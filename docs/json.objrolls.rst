==========================
json.objrolls - MapToolDoc
==========================

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

   .. rubric:: json.objrolls
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

         .. rubric:: json.objrolls() Function
            :name: json.objrolls-function

         .. container:: template_version

            • **Introduced in version 1.4.0.5**

         .. container:: template_description

            Is similar to `json.rolls() </rptools/wiki/json.rolls>`__
            but returns a JSON object.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     json.objrolls(names, stat, rolls)

         **Parameters**

         -  ``names`` - A JSON array containing the names to be used for
            each group.
         -  ``stat`` - A JSON array with the stat names.
         -  ``rolls`` - Either a single string containing a dice roll
            expression or a JSON array of dice roll expressions.

         This will generate rolls for each stat in a group for each
         "name". Rolls is either a single string with a roll expression
         in which case every stat will use same roll expression, or a
         json array with a roll expression for each stat (so must be
         same size as stat).

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",

               #. .. code:: de1

                             "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",

               #. .. code:: de1

                             "3d6"),2)}

         ::

            code:{  "henchman1":   {
                "Str": 10,
                "Dex": 12,
                "Con": 10,
                "Int": 10,
                "Wis": 8,
                "Chr": 12
              },
                   "henchman2":   {
                "Str": 11,
                "Dex": 10,
                "Con": 7,
                "Int": 13,
                "Wis": 9,
                "Chr": 7
              },
                   "henchman3":   {
                "Str": 10,
                "Dex": 10,
                "Con": 10,
                "Int": 12,
                "Wis": 15,
                "Chr": 13
              }}

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",

               #. .. code:: de1

                             "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",

               #. .. code:: de1

                             "['3d6+1', '3d6', '3d6', '3d6-2', '3d6', '2d6']"),2)}

         ::

            code:{  "henchman1":   {
                "Str": 11,
                "Dex": 12,
                "Con": 13,
                "Int": 8,
                "Wis": 10,
                "Chr": 11
              },
                    "henchman2":   {
                "Str": 12,
                "Dex": 11,
                "Con": 12,
                "Int": 8,
                "Wis": 12,
                "Chr": 3
              },
                    "henchman3":   {
                "Str": 12,
                "Dex": 13,
                "Con": 9,
                "Int": 8,
                "Wis": 13,
                "Chr": 7
              }}

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to JSON
            Datatypes </rptools/wiki/Introduction_to_JSON_Datatypes>`__
            , `json.rolls() </rptools/wiki/json.rolls>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.objrolls&oldid=7124"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.objrolls>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.objrolls>`__
            -  `Discussion </maptool/index.php?title=Talk:json.objrolls&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.objrolls>`__
            -  `View
               source </maptool/index.php?title=json.objrolls&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.objrolls&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.objrolls>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.objrolls>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.objrolls&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.objrolls&oldid=7124>`__
            -  `Page
               information </maptool/index.php?title=json.objrolls&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 March 2019, at 03:38.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
