============================
movedOverPoints - MapToolDoc
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

   .. rubric:: movedOverPoints
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *lastPath-format specified,
              define/explain return value, examples*

         .. rubric:: movedOverPoints() Function
            :name: movedoverpoints-function

         .. container:: template_version

            • **Introduced in version 1.3.b75**

         .. container:: template_description

            Use to check if a token has moved through a shape that is
            defined by an array of pixel coordinates (formatted like the
            one received from
            `getLastPath() </rptools/wiki/getLastPath>`__ or the
            ``onTokenMove`` event.
            Returns a JSON array with coordinates of all cells in the
            token's path that overlap with the area defined by the given
            points.

            Where each coordinate pair returned is dependent on the grid
            type:

            -  Square: Coordinates are the top-left corner.
            -  Hex: Coordinates are the center point of the cell.
            -  Isometric: Coordinates are the right-most point of the
               cell.
            -  Gridless: Returns just the top-left corner of the token's
               ending location.

            .. rubric:: Usage
               :name: usage

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        movedOverPoints(points)

                  #. .. code:: de1

                        movedOverPoints(points,path)

            **Parameters**

            -  ``points`` - JSON array of X/Y coordinate X/Y pairs that
               defines a polygon
            -  ``path`` - JSON array of X/Y coordinate such as that
               returned by `getLastPath() </rptools/wiki/getLastPath>`__

            .. rubric:: Example
               :name: example

            .. container:: template_example

               .. container:: mw-geshi mw-code mw-content-ltr

                  .. container:: mtmacro source-mtmacro

                     #. .. code:: de1

                           <!-- lets define a shape -->

                     #. .. code:: de1

                            

                     #. .. code:: de1

                           [h: jsonArray = json.append("",

                     #. .. code:: de1

                               json.set("", "x",   0, "y",   0),

                     #. .. code:: de2

                               json.set("", "x",   0, "y", 100),

                     #. .. code:: de1

                               json.set("", "x", 100, "y", 100),

                     #. .. code:: de1

                               json.set("", "x",   100, "y", 0)

                     #. .. code:: de1

                           )]

                     #. .. code:: de1

                            

                     #. .. code:: de2

                           <!-- check if token in context has moved through that shape -->

                     #. .. code:: de1

                           [r: movedOverPoints(jsonArray)]

               **With Second Parameter**

               .. container:: mw-geshi mw-code mw-content-ltr

                  .. container:: mtmacro source-mtmacro

                     #. .. code:: de1

                           [h: jsonArray = json.append("",

                     #. .. code:: de1

                               json.set("", "x", 250, "y", 250),

                     #. .. code:: de1

                               json.set("", "x", 250, "y", 550),

                     #. .. code:: de1

                               json.set("", "x", 550, "y", 550),

                     #. .. code:: de2

                               json.set("", "x", 550, "y", 250)

                     #. .. code:: de1

                           )]

                     #. .. code:: de1

                            

                     #. .. code:: de1

                           Last Path: [r: lastPath = getLastPath()]

                     #. .. code:: de1

                           <br>

                     #. .. code:: de2

                           Moved Over: [r: movedOverPoints(jsonArray,lastPath)]

         .. container:: printfooter

            Retrieved from
            "http://lmwcs.com/maptool/index.php?title=movedOverPoints&oldid=7354"

         .. container:: catlinks
            :name: catlinks

            .. container:: mw-normal-catlinks
               :name: mw-normal-catlinks

               `Categories </rptools/wiki/Special:Categories>`__:

               -  `Stub </rptools/wiki/Category:Stub>`__
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
            `Review </rptools/wiki/Category:Review>`__ >
            `Stub </rptools/wiki/Category:Stub>`__

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
               in </maptool/index.php?title=Special:UserLogin&returnto=movedOverPoints>`__

         .. container::
            :name: left-navigation

            .. container:: vectorTabs
               :name: p-namespaces

               .. rubric:: Namespaces
                  :name: p-namespaces-label

               -  `Page </rptools/wiki/movedOverPoints>`__
               -  `Discussion </maptool/index.php?title=Talk:movedOverPoints&action=edit&redlink=1>`__

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

               -  `Read </rptools/wiki/movedOverPoints>`__
               -  `View
                  source </maptool/index.php?title=movedOverPoints&action=edit>`__
               -  `View
                  history </maptool/index.php?title=movedOverPoints&action=history>`__

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
               -  `Recent
                  Changes </rptools/wiki/Special:RecentChanges>`__

         .. container:: portal
            :name: p-tb

            .. rubric:: Tools
               :name: p-tb-label

            .. container:: body

               -  `What links
                  here </rptools/wiki/Special:WhatLinksHere/movedOverPoints>`__
               -  `Related
                  changes </rptools/wiki/Special:RecentChangesLinked/movedOverPoints>`__
               -  `Special pages </rptools/wiki/Special:SpecialPages>`__
               -  `Printable
                  version </maptool/index.php?title=movedOverPoints&printable=yes>`__
               -  `Permanent
                  link </maptool/index.php?title=movedOverPoints&oldid=7354>`__
               -  `Page
                  information </maptool/index.php?title=movedOverPoints&action=info>`__

   .. container::
      :name: footer

      -  This page was last modified on 3 April 2019, at 15:27.

      -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
      -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
      -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

      -  |Powered by MediaWiki|

      .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
