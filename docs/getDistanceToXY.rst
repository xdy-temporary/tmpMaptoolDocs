============================
getDistanceToXY - MapToolDoc
============================

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

   .. rubric:: getDistanceToXY
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

            -  `1 getDistanceToXY()
               Function <#getDistanceToXY.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getDistanceToXY() Function
            :name: getdistancetoxy-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the distance to a target grid cell.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getDistanceToXY(x, y)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getDistanceToXY(x, y, units)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getDistanceToXY(x, y, units, source)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getDistanceToXY(x, y, units, source, metric)

         **Parameters**

         -  ``x`` - The X coordinate of the target grid cell.
         -  ``y`` - The Y coordinate of the target grid cell.
         -  ``units`` - If set to ``false``\ (``0``) the distance is
            returned in cells. Default is returning Distance Per Cell
            units.
         -  ``source`` - The id of the token to measure the distance
            from. Default is the current token.
         -  
         -  ``metric`` - The movement metric to use which defaults to
            the movement metric in the users preferences, the metric can
            be one of the following strings

            -  ``NO_GRID`` - The grid is ignored and straight line
               distance between the tokens is returned.
            -  ``ONE_TWO_ONE`` - First Diagonal movement costs 1, second
               2, and so on (Square grid only).
            -  ``ONE_ONE_ONE`` - Diagonal movement costs a single square
               (Square grid only).
            -  ``MANHATTAN`` - Diagonal movement costs 2 (Square grid
               only).
            -  ``NO_DIAGONALS`` - No diagonal movement is allowed
               (Square grid only).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To get the distance from the current token to 10,10.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: dist = getDistanceToXY(10, 10)]

            To get the distance between the *Altar* and 10, 10 in the
            number of squares or hexes.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: dist = getDistanceToXY(10, 10, 0, "Altar")]

            To get the distance between the *Altar* and 10, 10 in *map
            distance* units.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: dist = getDistanceToXY(10, 10, 1, "Altar")]

            To get the straight line distance between the *Altar* and
            10, 10.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: dist = getDistanceToXY(10, 10, 1, "Altar", "NO_GRID")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDistance() </rptools/wiki/getDistance>`__
            `getTokens() </rptools/wiki/getTokens>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b55** - Added the optional ``metric`` argument.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getDistanceToXY&oldid=3054"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Distance
               Function </rptools/wiki/Category:Distance_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Distance
         Function </rptools/wiki/Category:Distance_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getDistanceToXY>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getDistanceToXY>`__
            -  `Discussion </maptool/index.php?title=Talk:getDistanceToXY&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getDistanceToXY>`__
            -  `View
               source </maptool/index.php?title=getDistanceToXY&action=edit>`__
            -  `View
               history </maptool/index.php?title=getDistanceToXY&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getDistanceToXY>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getDistanceToXY>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getDistanceToXY&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getDistanceToXY&oldid=3054>`__
            -  `Page
               information </maptool/index.php?title=getDistanceToXY&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 14 April 2009, at 07:18.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
