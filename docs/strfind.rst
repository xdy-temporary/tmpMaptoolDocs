====================
strfind - MapToolDoc
====================

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

   .. rubric:: strfind
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

         .. rubric:: strfind() Function
            :name: strfind-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Finds and extracts substrings from a string. ``strfind()``
            is used to match a pattern against an input string and
            extract all of the capture groups. The function returns an
            id which can be used with other functions to extract the
            information. The supplied pattern is a `regular
            expression </rptools/wiki/Macros:regular_expression>`__.
            Functions related to ``strfind()``:

            -  `getFindCount(id) </rptools/wiki/Macros:Functions:getFindCount>`__
            -  `getGroupCount(id) </rptools/wiki/Macros:Functions:getGroupCount>`__
            -  `getGroup(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroup>`__
            -  `getGroupStart(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroupStart>`__
            -  `getGroupEnd(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroupEnd>`__

            Both ``groupNo`` and ``matchNo`` start at 1, the special
            group number ``0`` returns the whole pattern match.

            *Groups* are the regex parts in ``"("`` parenthesis ``")"``,
            so 1 returns the string that matches the first regex
            statement in ``()``, 2 returns the second, etc.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     strfind(str,  pattern)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [h: id = strfind("This is a really useless test", "(\\S+)\\s+(\\S+)\\s*")] 

                  #. .. code-block:: none

                            [r: getGroupCount(id)]

                  #. .. code-block:: none

                            [r: getFindCount(id)] 

                  #. .. code-block:: none

                            [r: getGroup(id, 1, 1)]  

                  #. .. code:: de2

                            [r: getGroup(id, 2, 2)]

            Returns:

            ::

                  2 
                  3 
                  This 
                  really 
                  This is

            | 
            | A slightly more usefull and advanced example:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [h:id = strfind("Command-20, Sleight of Hand 10, Knowledge (Arcana) +5", "([^,]*?)\\s?([-+]?\\d+)(,|\$)")]
                     <b>First group</b><br>
                     [r,count(getFindCount(id), "<b>Next group</b><br>"), code: {
                       "[r:getGroup(id, roll.count+1, 0)]" <br>
                         "[r:getGroup(id, roll.count+1, 1)]" <br>
                         "[r:getGroup(id, roll.count+1, 2)]" <br>
                     } ]

            Returns:

            ::

                  First group 
                  "Command-20," 
                  "Command" 
                  "-20" 
                  Next group 
                  " Sleight of Hand 10," 
                  " Sleight of Hand" 
                  "10" 
                  Next group 
                  " Knowledge (Arcana) +5" 
                  " Knowledge (Arcana)" 

            "5"

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=strfind&oldid=5879"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `String
               Function </rptools/wiki/Category:String_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `String
         Function </rptools/wiki/Category:String_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=strfind>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/strfind>`__
            -  `Discussion </maptool/index.php?title=Talk:strfind&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/strfind>`__
            -  `View
               source </maptool/index.php?title=strfind&action=edit>`__
            -  `View
               history </maptool/index.php?title=strfind&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/strfind>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/strfind>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=strfind&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=strfind&oldid=5879>`__
            -  `Page
               information </maptool/index.php?title=strfind&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 17 February 2012, at 15:52.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
