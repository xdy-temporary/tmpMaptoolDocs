=========================
JSON Sorting - MapToolDoc
=========================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: JSON Sorting
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         Following is the full macro code for the `Sorting Nested JSON
         Objects <Sorting_Nested_JSON_Objects>`__ How To.
         Line numbers are excluded to ease cutting and pasting.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  <!--Set Up Sample Object-->
                   
                  [h:troll = json.set("{}", "name", "Troll", "HD", 4, "HP", 75)]
                  [h:orc = json.set("{}", "name", "Orc", "HD", 3, "HP", 13)]
                  [h:goblin = json.set("{}", "name", "Goblin", "HD", 2, "HP", 6)]
                  [h:gnoll = json.set("{}", "name", "Gnoll", "HD", 3, "HP", 19)]
                  [h:kobold=json.set("{}", "name", "Kobold", "HD", 1, "HP", 4)]
                  [h:monsters = json.set("{}", "Troll", troll, "Orc", orc, "Goblin", 
                                         goblin, "Gnoll", gnoll, "Kobold", kobold)]
                   
                  <!--Request User Input for Sorting-->
                   
                  [h:status = input(
                      "whichKey|name,HD,HP|Pick Sorting Key|LIST|SELECT=0 VALUE=STRING",
                      "whichDirection|A+,A-,N+,N-|Direction (A+/- for strings, N+/- for numbers!)"+
                          "|LIST|SELECT=0 VALUE=STRING"
                  )]
                  [h:abort(status)]
                   
                  [h,if(substring(whichDirection,1)=="+"): dirString = "ascending"; dirString = "descending"]
                   
                  <!--Initialize Variables-->
                   
                  [h:sortObj=monsters]
                  [h:sortKey = whichKey]
                  [h:sortDirection = whichDirection]
                  [h:sortObjContentList = json.fields(sortObj)]
                  [h:keyList = ""] 
                  [h:sortedJSON = "{}"]
                   
                   
                  <!--Get value corresponding to sortKey for each nested object and append to keyList-->
                   
                  [h,foreach(item, sortObjContentList),CODE:
                  {
                     [h:itemDetail = json.get(sortObj,item)]
                     [h: keyList = listAppend(keyList, json.get(itemDetail, sortKey))]
                  }]
                   
                  <!--Sort keyList based on the direction input by the user-->
                   
                  [h:keyList = listSort(keyList, sortDirection)]
                   
                   
                  <!--
                  Loop through keyList, and for each element, find the matching nested object(s) 
                  and add them to the new sortedJSON object
                  -->
                   
                  [h,foreach(key,keyList),CODE:
                  {
                     [foreach(object,sortObj),CODE:
                     {
                       [objectDetail = json.get(sortObj,object)]
                       [h:sortOnValue = json.get(objectDetail, sortKey)]
                       [if(sortOnValue == key): sortedJSON=json.set(sortedJSON, object, objectDetail);""]
                     }]
                  }]
                   
                  <!--Output the Results-->
                   
                  JSON Object sorted by [r:whichKey], [r:dirString]:<br>
                  <pre>[r:json.indent(sortedJSON, 3)]</pre>

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=JSON_Sorting&oldid=2622"

