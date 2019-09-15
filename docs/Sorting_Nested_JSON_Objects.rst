========================================
Sorting Nested JSON Objects - MapToolDoc
========================================

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

   .. rubric:: Sorting Nested JSON Objects
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

         JSON Objects can contain an arbitrary number of keys and values
         (for which the value may itself be another JSON object). For
         example, a nested JSON object called "Monsters" might look like
         this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     {

               #. .. code:: de1

                      "Troll":

               #. .. code:: de1

                       {

               #. .. code:: de1

                         "name":"Troll",

               #. .. code:: de2

                         "HD":4,

               #. .. code:: de1

                         "HP":75

               #. .. code:: de1

                       },

               #. .. code:: de1

                      "Orc":

               #. .. code:: de1

                       {

               #. .. code:: de2

                         "name":"Orc",

               #. .. code:: de1

                         "HD":3,

               #. .. code:: de1

                         "HP":22

               #. .. code:: de1

                       }

               #. .. code:: de1

                     }

         Note that each value in the key-value pairs in the above object
         is actually a complete JSON object in its own right.

         It is occasionally useful to be able to sort a JSON object that
         contains *other* JSON objects based on a value in one of the
         "sub-objects." For instance, if a JSON object exists that
         contains token names and distances to those tokens from a given
         point, one may want to sort the JSON so that the nearest
         objects are first, and the farthest are last.

         Or, using the above "Monsters" example, one may wish to sort it
         by **name**, or by **HP**, or by **HD**.

         The following macro routine is a generic method to sort JSON
         objects based on an arbitrary value within a nested object.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Assumptions <#Assumptions>`__
            -  `2 Macro Code and
               Discussion <#Macro_Code_and_Discussion>`__

               -  `2.1 Create Sample Object <#Create_Sample_Object>`__
               -  `2.2 Request Sorting Key and Sort Direction from
                  User <#Request_Sorting_Key_and_Sort_Direction_from_User>`__
               -  `2.3 Set Basic Variables <#Set_Basic_Variables>`__
               -  `2.4 Extract the Value of sortKey from each Nested
                  Object <#Extract_the_Value_of_sortKey_from_each_Nested_Object>`__
               -  `2.5 Iterating through keyList and Each Nested
                  Object <#Iterating_through_keyList_and_Each_Nested_Object>`__
               -  `2.6 Outputting the Results in an Attractive
                  Fashion <#Outputting_the_Results_in_an_Attractive_Fashion>`__

         .. rubric:: Assumptions
            :name: assumptions

         -  This macro requires the use of a JSON object supporting
            version of MapTool; it was written and tested in version
            1.3.b53.
         -  The macro is generic, and will run using any given JSON
            object conforming to the general "nested object" structure.
            In this case, a nested JSON object is created in the
            beginning so that there is a sample object to sort.
            **However**: this routine should be applicable to JSON
            arrays of objects as well - it would simply require using
            the index of the nested object rather than the nested
            object's key.
         -  It can be unclear which object is being discussed when you
            have multiply nested objects. In the following explanation,
            "nested object" will always refer to an object contained
            *within a larger JSON*. So, the larger object is
            **Monsters**, while **Troll** would be a *nested object.*

         .. rubric:: Macro Code and Discussion
            :name: macro-code-and-discussion

         Please see the `full macro
         code </rptools/wiki/Tutorials:Macros:JSONSortingFullCode>`__
         for the complete macro.

         .. rubric:: Create Sample Object
            :name: create-sample-object

         This sequence simply creates a sample object to practice
         sorting. In actual use, you may wish to pass an object as an
         argument, or pull an object from a token's properties, as
         necessary.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:troll = json.set("{}", "name", "Troll", "HD", 4, "HP", 75)]

               #. .. code:: de1

                     [h:orc = json.set("{}", "name", "Orc", "HD", 3, "HP", 13)]

               #. .. code:: de1

                     [h:goblin = json.set("{}", "name", "Goblin", "HD", 2, "HP", 6)]

               #. .. code:: de1

                     [h:gnoll = json.set("{}", "name", "Gnoll", "HD", 3, "HP", 19)]

               #. .. code:: de2

                     [h:kobold=json.set("{}", "name", "Kobold", "HD", 1, "HP", 4)]

               #. .. code:: de1

                     [h:monsters = json.set("{}", "Troll", troll, "Orc", orc, "Goblin", goblin, "Gnoll", gnoll, "Kobold", kobold)]

         .. rubric:: Request Sorting Key and Sort Direction from User
            :name: request-sorting-key-and-sort-direction-from-user

         This section is also optional (and not useful if this macro
         will be used as a function/called macro), but for the example
         code it makes it easier to experiment with. This section uses
         `input() </rptools/wiki/input>`__ to gather user input, and
         `abort() </rptools/wiki/abort>`__ to halt processing if the
         user hits "Cancel." Finally, it uses an
         `IF(): </rptools/wiki/Macros:Branching_and_Looping#IF_Option>`__
         roll option to set a variable with a "friendly" indicator of
         sort direction, which will be used at the end in the final
         output.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:status = input(

               #. .. code:: de1

                     "whichKey|name,HD,HP|Pick Sorting Key|LIST|SELECT=0 VALUE=STRING",

               #. .. code:: de1

                     "whichDirection|A+,A-,N+,N-|Direction (A+/- for strings, N+/- for numbers!)|LIST|SELECT=0 VALUE=STRING"

               #. .. code:: de1

                     )]

               #. .. code:: de2

                     [h:abort(status)]

               #. .. code:: de1

                      

               #. .. code:: de1

                     [h,if(substring(whichDirection,1)=="+"): dirString = "ascending"; dirString = "descending"]

         .. rubric:: Set Basic Variables
            :name: set-basic-variables

         This segment initializes some variables that will be used
         later:

         -  *sortObj* is the object to be sorted (in this case, the JSON
            Object **Monsters**)
         -  *sortOn* is the value on which to sort (**name**, **HD**, or
            **HP**)
         -  *sortDirection* is the direction of the sort, which will be
            passed to `listSort() </rptools/wiki/listSort>`__
         -  *sortObjContentList* is a list - created using
            `json.fields() </rptools/wiki/json.fields>`__ - of each
            nested object within **Monsters**; effectively it is a list
            of the "names" of each monster
         -  *keyList* is a list that will contain the value that
            corresponds to the thing we're sorting on - so if you choose
            to sort by **name**, then *keyList* will ultimately contain
            the value of **name** for each monster in the **Monsters**
            object
         -  *sortedJSON* will hold the new, nicely sorted JSON object;
            the original object will be unchanged.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:sortObj=monsters]

               #. .. code:: de1

                     [h:sortKey = whichKey]

               #. .. code:: de1

                     [h:sortDirection = whichDirection]

               #. .. code:: de1

                     [h:sortObjContentList = json.fields(sortObj)]

               #. .. code:: de2

                     [h:keyList = ""] 

               #. .. code:: de1

                     [h:sortedJSON = "{}"]

         .. rubric:: Extract the Value of sortKey from each Nested
            Object
            :name: extract-the-value-of-sortkey-from-each-nested-object

         Here, we use FOREACH() to loop through each element in
         *sortObjContentList* (in other words, go one-by-one through the
         list of monster names). The FOREACH() option lets us say that
         *item* holds the value of each of those (so for the first pass,
         *item* holds the first monster name in the list, and on the
         second pass, it moves to the next, and so on). We need to do
         this so that we can extract the detailed information about each
         monsters from the **Monsters** object (in this case, we assign
         the detailed information to a new variable called
         *itemDetail*).

         With the nested objects extracted, we can then retrieve the
         value of the thing we're sorting on by using
         `json.get() </rptools/wiki/json.get>`__ on the variable
         *itemDetail*. We stick that value in the previously empty list
         *keyList*.

         Finally, once we've gone through each nested object held within
         **Monsters** and each nested object's value for our chosen sort
         (remember, we put that information in the variable *sortKey*)
         has been added to *keyList*, we're finished with the loop.

         Now we actually can determine what the right order will
         ultimately be - we sort *keyList* using
         `listSort() </rptools/wiki/listSort>`__ based on the direction
         specified by the user. **This is a critical step!** We've gone
         through each object, and figured out what the *value* of the
         thing we're sorting on is - so if we're sorting on "name",
         we've gone and actually retrieved each object's *name*, and put
         it in a list with the others. We then sort that list, which
         tells us the final order to use when we reassemble the main
         object!

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h,foreach(item, sortObjContentList),CODE:

               #. .. code:: de1

                     {

               #. .. code:: de1

                        [h:itemDetail = json.get(sortObj,item)]

               #. .. code:: de1

                        [h: keyList = listAppend(keyList, json.get(itemDetail, sortKey))]

               #. .. code:: de2

                     }]

               #. .. code:: de1

                      

               #. .. code:: de1

                     [h:keyList = listSort(keyList, sortDirection)]

         .. rubric:: Iterating through keyList and Each Nested Object
            :name: iterating-through-keylist-and-each-nested-object

         This is the most complex part of the routine.
         `FOREACH(): </rptools/wiki/Macros:Branching_and_Looping#FOREACH_Option>`__
         through each element in the variable *keyList* (which, you will
         recall, contains the values corresponding to *sortKey* for each
         nested object). For *each* element in *keyList*, we then loop
         through *all* of the nested objects in **Monsters** to see
         which one(s) match up to the current element of *keyList*.

         So, for example, if the current value - *key* - in the outer
         loop is 4, and we are sorting by "HD", the inner loop will
         iterate through each nested object and check to see if the
         value of "HD" for that nested object is equal to 4.

         If a match is found, the matching nested object is added to
         *sortedJSON* using `json.set() </rptools/wiki/json.set>`__. In
         this fashion, we're using *keyList* to tell us what order the
         final nested objects should be in, and we then just need to go
         through our nested objects, setting them in that order via the
         following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h,foreach(key,keyList),CODE:

               #. .. code:: de1

                     {

               #. .. code:: de1

                        [foreach(object,sortObj),CODE:

               #. .. code:: de1

                        {

               #. .. code:: de2

                          [objectDetail = json.get(sortObj,object)]

               #. .. code:: de1

                          [h:sortOnValue = json.get(objectDetail, sortKey)]

               #. .. code:: de1

                          [if(sortOnValue == key): sortedJSON=json.set(sortedJSON, object, objectDetail);""]

               #. .. code:: de1

                        }]

               #. .. code:: de1

                     }]

         .. rubric:: Outputting the Results in an Attractive Fashion
            :name: outputting-the-results-in-an-attractive-fashion

         The final step is to output results. The use of
         `json.indent() </rptools/wiki/json.indent>`__ here simply makes
         the sorted JSON object easy to read.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     JSON Object sorted by [r:whichKey], [r:dirString]:<br>

               #. .. code:: de1

                     <pre>[r:json.indent(sortedJSON, 3)]</pre>

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Sorting_Nested_JSON_Objects&oldid=2618"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `How To </rptools/wiki/Category:How_To>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `How
         To </rptools/wiki/Category:How_To>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Sorting+Nested+JSON+Objects>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Sorting_Nested_JSON_Objects>`__
            -  `Discussion </rptools/wiki/Talk:Sorting_Nested_JSON_Objects>`__

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

            -  `Read </rptools/wiki/Sorting_Nested_JSON_Objects>`__
            -  `View
               source </maptool/index.php?title=Sorting_Nested_JSON_Objects&action=edit>`__
            -  `View
               history </maptool/index.php?title=Sorting_Nested_JSON_Objects&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Sorting_Nested_JSON_Objects>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Sorting_Nested_JSON_Objects>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Sorting_Nested_JSON_Objects&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Sorting_Nested_JSON_Objects&oldid=2618>`__
            -  `Page
               information </maptool/index.php?title=Sorting_Nested_JSON_Objects&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 April 2009, at 13:51.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
