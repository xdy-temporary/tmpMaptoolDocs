===========================
hasLightSource - MapToolDoc
===========================

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

   .. rubric:: hasLightSource
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

            -  `1 hasLightSource()
               Function <#hasLightSource.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: hasLightSource() Function
            :name: haslightsource-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns 1 if the `Current
            Token </rptools/wiki/Current_Token>`__ has any `light
            sources </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            that match the criteria passed in or 0 if there are no
            matches. If no arguments are passed to the function then it
            will return 1 if any `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            is on. If only the first argument is passed it will return 1
            if any `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            of that `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__
            is on. If both arguments are passed to the function it will
            return 1 if the `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            with the specified name and specified `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__
            is on.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hasLightSource()

               #. .. code-block:: none

                     hasLightSource(type)

               #. .. code-block:: none

                     hasLightSource(type, name)

               #. .. code-block:: none

                     hasLightSource(type, name, id)

               #. .. code:: de2

                     hasLightSource(type, name, id, mapname)

         **Parameters**

         -  ``type`` - The `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__,
            (e.g. "Generic", "D20"). If "*" is entered, all light
            sources types are checked. Defaults to "*".
         -  ``name`` - the name of the `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__.
            If "*" is entered, all light sources names are checked.
            Defaults to "*".
         -  ``id`` - The token ``id`` of the token which is checked for
            light sources, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Check to see if any light source is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource()]

            Check to see if a "D20" lamp is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource("D20", "Lamp - 15")]

            Check to see if any "D20" light source is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource("D20")

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options. Changed behavior if ``type`` or ``name`` are set
               to "*".

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=hasLightSource&oldid=7548"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Light
               Function </rptools/wiki/Category:Light_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Light
         Function </rptools/wiki/Category:Light_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=hasLightSource>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/hasLightSource>`__
            -  `Discussion </maptool/index.php?title=Talk:hasLightSource&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/hasLightSource>`__
            -  `View
               source </maptool/index.php?title=hasLightSource&action=edit>`__
            -  `View
               history </maptool/index.php?title=hasLightSource&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/hasLightSource>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/hasLightSource>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=hasLightSource&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=hasLightSource&oldid=7548>`__
            -  `Page
               information </maptool/index.php?title=hasLightSource&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 16 August 2019, at 19:51.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
