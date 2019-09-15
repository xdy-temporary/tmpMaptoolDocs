=======================
listFormat - MapToolDoc
=======================

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

   .. rubric:: listFormat
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

         .. rubric:: listFormat() Function
            :name: listformat-function

         .. container:: template_description

            Returns a custom-formatted version of the list.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [ listFormat(list, listFormat, itemFormat, separator) ]

               #. .. code:: de1

                     [ listFormat(list, listFormat, itemFormat, separator, delim) ]

         -  listFormat is a string that is emitted once. It should
            contain the text "%list", which is replaced with the
            formatted items.
         -  itemFormat is emitted once per item. Each instance of
            "%item" in the string is replaced with the value of the list
            item.
         -  separator is emitted in between the formatted items.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [ listFormat("apple,bear,cat", "BEGIN LIST<br>%list<br>END LIST", "This item is: %item", "<br>") ]

            (prints items on separate lines)

            Convert a string list to html list:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [R: listFormat( "apple, bear, cat", "<ul>%list</ul>", "<li>%item</li>", "" ) ]

            Produces:

            -  apple
            -  bear
            -  cat

            | 
            | Create an option list input (drop-down list selection) for
              an html form, with the names of selected tokens:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [R: listFormat( getSelectedNames( "%%" ), 

                  #. .. code:: de1

                            "<select name='test'>%list</select>", 

                  #. .. code:: de1

                            "<option value='%item'>%item</option>", 

                  #. .. code:: de1

                            "",  

                  #. .. code:: de2

                            "%%" ) 

                  #. .. code:: de1

                        ]

            The first argument is the list, returned by
            `getSelectedNames() </rptools/wiki/getSelectedNames>`__: it
            has a delimiter specified ("%%"), to avoid PC names with
            commas or anything other than "%%" from appearing as more
            than one item. The second argument specifies html (text) to
            go around the entire formatted *list*, and the third is html
            to wrap around each *item* in the list. The fourth argument
            is blank (empty), since no separator between items is needed
            in this case. The fifth argument is usually optional, but in
            this case is the same delimiter specified in
            getSelectedNames(), to allow listFormat to find each item in
            the list.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listFormat&oldid=4155"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `String List
               Function </rptools/wiki/Category:String_List_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `String
         List Function </rptools/wiki/Category:String_List_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=listFormat>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/listFormat>`__
            -  `Discussion </maptool/index.php?title=Talk:listFormat&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/listFormat>`__
            -  `View
               source </maptool/index.php?title=listFormat&action=edit>`__
            -  `View
               history </maptool/index.php?title=listFormat&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/listFormat>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/listFormat>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=listFormat&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=listFormat&oldid=4155>`__
            -  `Page
               information </maptool/index.php?title=listFormat&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 23 March 2010, at 18:05.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
