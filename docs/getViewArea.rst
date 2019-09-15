========================
getViewArea - MapToolDoc
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

   .. rubric:: getViewArea
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

            -  `1 getViewArea()
               Function <#getViewArea.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getViewArea() Function
            :name: getviewarea-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns the limits of the visible area of the map window,
            given in either pixels or cell coordinates depending on the
            first parameter. The result is in a ";" delimited String as
            default or can be configured by setting the delimiter or
            using Json.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getViewArea()

               #. .. code-block:: none

                     getViewArea(pixels)

               #. .. code-block:: none

                     getViewArea(pixels, delim)

         **Parameters**

         -  ``pixels`` - if set to true (1) means the returned
            coordinates are measured in pixels. If set to false (0) the
            returned coordinates are measured in map cells. Defaults to
            ``true``.
         -  ``delim`` - if set to "json" means the returned coordinates
            are defined in JSON style. Otherwise a String property list
            is returning using ``delim`` as a delimiter. Defaults to
            ``;``.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Get the viewport dimensions of the current client:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getViewArea()] <!-- Default pixels -->

                  #. .. code-block:: none

                        [r: getViewArea(0)] <!-- in Grid Cells -->

                  #. .. code-block:: none

                        [r: getViewArea(1)] <!-- in Pixels -->

                  #. .. code-block:: none

                        [r: getViewArea(0, "json")] <!-- Cells as JSON -->

                  #. .. code:: de2

                        [r: getViewArea(1, "json")] <!-- Pixels as JSON -->

                  #. .. code-block:: none

                        [r: getViewArea(0, ",")] <!-- Cells as "," separated String properties: -->

                  #. .. code-block:: none

                        [r: getViewArea(1, ";")] <!-- Pixels as ";" separated String properties: -->

            Output:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=17; endY=12 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616 

                  #. .. code-block:: none

                        {"startX":0,"startY":0,"endX":886,"endY":616} 

                  #. .. code:: de2

                        {"startX":0,"startY":0,"endX":886,"endY":616} 

                  #. .. code-block:: none

                        startX=0, startY=0, endX=886, endY=616 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setViewArea() </rptools/wiki/setViewArea>`__,
            `goto() </rptools/wiki/goto>`__,
            `setZoom() </rptools/wiki/setZoom>`__,
            `getZoom() </rptools/wiki/getZoom>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getViewArea&oldid=7442"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getViewArea>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getViewArea>`__
            -  `Discussion </maptool/index.php?title=Talk:getViewArea&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getViewArea>`__
            -  `View
               source </maptool/index.php?title=getViewArea&action=edit>`__
            -  `View
               history </maptool/index.php?title=getViewArea&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getViewArea>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getViewArea>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getViewArea&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getViewArea&oldid=7442>`__
            -  `Page
               information </maptool/index.php?title=getViewArea&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 13 July 2019, at 11:42.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
