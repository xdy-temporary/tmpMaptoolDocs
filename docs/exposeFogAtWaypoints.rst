=================================
exposeFogAtWaypoints - MapToolDoc
=================================

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

   .. rubric:: exposeFogAtWaypoints
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

            -  `1 exposeFogAtWaypoints()
               Function <#exposeFogAtWaypoints.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: exposeFogAtWaypoints() Function
            :name: exposefogatwaypoints-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.8**

         .. container:: template_description

            Returns a string ``(Enabled/Disabled)`` indicating whether
            the **Expose Fog At Waypoints** option is set in the MapTool
            Map menu. This menu option toggles the setting for the
            currently displayed map. This setting affects when automatic
            exposure of Fog of War (FoW) will be performed after a token
            has been moved. With it enabled, FoW will only be exposed at
            any waypoints set by the user along the tokens path plus the
            stopping point. If not enabled, FoW will be exposed from
            every cell along the token's path.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     exposeFogAtWaypoints()

         **Parameters** None.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: empty = exposeFogAtWaypoints()]

            **Returns:**

            -  Disabled - Option is disabled.
            -  Enabled - Option is enabled.

            .. rubric:: See Also
               :name: see-also

            .. container:: template_also

               `exposeFOW() </rptools/wiki/exposeFOW>`__,
               `toggleFoW() </rptools/wiki/toggleFoW>`__

         .. container:: printfooter

            Retrieved from
            "http://lmwcs.com/maptool/index.php?title=exposeFogAtWaypoints&oldid=7171"

         .. container:: catlinks
            :name: catlinks

            .. container:: mw-normal-catlinks
               :name: mw-normal-catlinks

               `Categories </rptools/wiki/Special:Categories>`__:

               -  `Macro
                  Function </rptools/wiki/Category:Macro_Function>`__
               -  `FoW </rptools/wiki/Category:FoW>`__

            --------------

            `FoW </rptools/wiki/Category:FoW>`__ >
            `FoW </rptools/wiki/Category:FoW>`__
            `MapTool </rptools/wiki/Category:MapTool>`__ >
            `Macro </rptools/wiki/Category:Macro>`__ > `Macro
            Function </rptools/wiki/Category:Macro_Function>`__

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
               in </maptool/index.php?title=Special:UserLogin&returnto=exposeFogAtWaypoints>`__

         .. container::
            :name: left-navigation

            .. container:: vectorTabs
               :name: p-namespaces

               .. rubric:: Namespaces
                  :name: p-namespaces-label

               -  `Page </rptools/wiki/exposeFogAtWaypoints>`__
               -  `Discussion </maptool/index.php?title=Talk:exposeFogAtWaypoints&action=edit&redlink=1>`__

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

               -  `Read </rptools/wiki/exposeFogAtWaypoints>`__
               -  `View
                  source </maptool/index.php?title=exposeFogAtWaypoints&action=edit>`__
               -  `View
                  history </maptool/index.php?title=exposeFogAtWaypoints&action=history>`__

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
                  here </rptools/wiki/Special:WhatLinksHere/exposeFogAtWaypoints>`__
               -  `Related
                  changes </rptools/wiki/Special:RecentChangesLinked/exposeFogAtWaypoints>`__
               -  `Special pages </rptools/wiki/Special:SpecialPages>`__
               -  `Printable
                  version </maptool/index.php?title=exposeFogAtWaypoints&printable=yes>`__
               -  `Permanent
                  link </maptool/index.php?title=exposeFogAtWaypoints&oldid=7171>`__
               -  `Page
                  information </maptool/index.php?title=exposeFogAtWaypoints&action=info>`__

   .. container::
      :name: footer

      -  This page was last modified on 5 March 2019, at 14:19.

      -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
      -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
      -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

      -  |Powered by MediaWiki|

      .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
