======================
json.sort - MapToolDoc
======================

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

   .. rubric:: json.sort
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

         .. rubric:: json.sort() Function
            :name: json.sort-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Used to sort JSON arrays. If the array contains only
            numbers, they are sorted numerically; otherwise, the values
            are sorted as strings alphabetically.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array, direction)

         If you have a `JSON Array </rptools/wiki/JSON_Array>`__ that
         contains `JSON Objects </rptools/wiki/JSON_Object>`__

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array, direction, key1, ..., keyN)

         **Parameters**

         -  ``array`` - The JSON array to sort.
         -  ``direction`` - Defaults to ``"ascending"``, acceptable
            values:

            -  ``"ascending"``
            -  ``"descending"``
            -  ``"ascend"``
            -  ``"descend"``
            -  ``"asc"``
            -  ``"desc"``
            -  ``"a"``
            -  ``"d"``

         -  ``key1, ..., keyN`` - The keys in the `JSON
            Objects </rptools/wiki/JSON_Object>`__ contained within the
            `JSON Array </rptools/wiki/JSON_Array>`__ used for sorting.
            All `JSON Objects </rptools/wiki/JSON_Object>`__ must
            contain these fields.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Sorting a `JSON Array </rptools/wiki/JSON_Array>`__
            containing numbers.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("[1,4,5,6,2,1,9,20,1]")]

            Produces ``[1,1,1,2,4,5,6,9,20]``

            Sorting a `JSON Array </rptools/wiki/JSON_Array>`__
            containing strings.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("['Hero', 'Dragon', 'Elf', 'Wolf', 'Mage', 'Eagle', 'Troll']")]

            Produces
            ``["Dragon","Eagle","Elf","Hero","Mage","Troll","Wolf"]``

            Sorting a mixture of numbers and strings (all will be
            treated as string).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("['Hero', 3, 'Elf', 'Wolf', 100, 'Eagle', 'Troll']")]

            Produces ``[100,3,"Eagle","Elf","Hero","Troll","Wolf"]``

            Sorting objects by a single string key

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "name")]

            Produces

            ``[{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Mage","HP":20},{"name":"Troll","HP":15},{"name":"Wolf","HP":5}]``

            Sorting objects by a single numeric key

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "HP")]

            Produces

            ``[{"name":"Wolf","HP":5},{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]``

            Sorting objects by a two keys, first HP then Name.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "HP", "name")]

            Produces

            ``[{"name":"Eagle","HP":5},{"name":"Wolf","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.sort&oldid=7128"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `JSON Function </rptools/wiki/Category:JSON_Function>`__
            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `JSON
         Function </rptools/wiki/Category:JSON_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.sort>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.sort>`__
            -  `Discussion </maptool/index.php?title=Talk:json.sort&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.sort>`__
            -  `View
               source </maptool/index.php?title=json.sort&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.sort&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.sort>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.sort>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.sort&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.sort&oldid=7128>`__
            -  `Page
               information </maptool/index.php?title=json.sort&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 March 2019, at 03:47.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
