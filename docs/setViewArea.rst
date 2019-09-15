========================
setViewArea - MapToolDoc
========================

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

   .. rubric:: setViewArea
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setViewArea()
               Function <#setViewArea.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setViewArea() Function
            :name: setviewarea-function

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Sets the currently viewed screen area, set by two sets of
            cell coordinates, so that the two cells are at the edge of
            the screen. If the map is "gridless", the coordinates will
            be pixel coordinates. A final optional parameter causes the
            view of any connected players to be set the same. Only GMs
            or trusted macros can trigger the view of all players to
            change.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     setViewArea(startX, startY, endX, endY [, pixels [, allPlayers]])

         **Parameters**

         -  ``startX`` - the x coordinate of the cell that will mark the
            upper left corner of the displayed area.
         -  ``startY`` - the y coordinate of the cell that will mark the
            upper left corner of the displayed area.
         -  ``endX`` - the x coordinate of the cell that will mark the
            lower right corner of the displayed area.
         -  ``endY`` - the x coordinate of the cell that will mark the
            lower right corner of the displayed area
         -  ``pixels`` - an optional parameter that if set to true (1)
            means the coordinates are measured in pixels. If set to
            false (0) the coordinates are measured in map cells.
            Defaults to true (1).
         -  ``allPlayers`` - Optional: If set to true (1) and called
            from a trusted macro, all players views will be set.
            Defaults to 0

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Set the viewport of the current client such that it at least
            sees the corners of the area with the following CELL
            coordinates:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:setViewArea(0,0,30,20, 0)]

            When the GM runs the macro change the viewport in PIXEL
            coordinates on ALL clients, else only on the current client:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:setViewArea(0, 0, 300, 200, 1, isGM())]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getViewArea() </rptools/wiki/getViewArea>`__,
            `getTokenY() </rptools/wiki/getTokenY>`__,
            `goto() </rptools/wiki/goto>`__,
            `setZoom() </rptools/wiki/setZoom>`__,
            `getZoom() </rptools/wiki/getZoom>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setViewArea&oldid=7280"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Miscellaneous
         Function </rptools/wiki/Category:Miscellaneous_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=setViewArea>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/setViewArea>`__
            -  `Discussion </maptool/index.php?title=Talk:setViewArea&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/setViewArea>`__
            -  `View
               source </maptool/index.php?title=setViewArea&action=edit>`__
            -  `View
               history </maptool/index.php?title=setViewArea&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/setViewArea>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/setViewArea>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=setViewArea&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=setViewArea&oldid=7280>`__
            -  `Page
               information </maptool/index.php?title=setViewArea&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 17 March 2019, at 13:41.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
