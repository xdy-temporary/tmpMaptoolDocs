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
         Objects </rptools/wiki/Sorting_Nested_JSON_Objects>`__ How To.
         Line numbers are excluded to ease cutting and pasting.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

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

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=JSON+Sorting>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/JSON_Sorting>`__
            -  `Discussion </maptool/index.php?title=Talk:JSON_Sorting&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/JSON_Sorting>`__
            -  `View
               source </maptool/index.php?title=JSON_Sorting&action=edit>`__
            -  `View
               history </maptool/index.php?title=JSON_Sorting&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/JSON_Sorting>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/JSON_Sorting>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=JSON_Sorting&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=JSON_Sorting&oldid=2622>`__
            -  `Page
               information </maptool/index.php?title=JSON_Sorting&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 April 2009, at 13:57.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
