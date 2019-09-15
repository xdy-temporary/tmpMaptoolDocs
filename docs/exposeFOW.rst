======================
exposeFOW - MapToolDoc
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

   .. rubric:: exposeFOW
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

            -  `1 exposeFOW() Function <#exposeFOW.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: exposeFOW() Function
            :name: exposefow-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b76**

         .. container:: template_description

            Clears the Fog of War (FOW) for all **selected** tokens on
            the current map according to their sight settings. An
            optional ``mapName`` parameter allows exposure on maps other
            than the current map. *Note that unless the optional
            ``tokens`` parameter is provided there must be tokens
            selected on the map.*

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  exposeFOW()
                  exposeFOW(mapname)
                  exposeFOW(mapName,tokens)
                  exposeFOW(mapName,tokens, delim)

         **Parameters**

         -  ``mapname`` - Optional map name.
         -  ``tokens`` - Optional delimited string list or JSON array of
            tokens.
         -  ``delim`` - Delimiter for tokens parameter. Defaults to ",".
            Use "json" for a JSON array.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Expose FoW for selected tokens on current map. -->

                  #. .. code-block:: none

                        [h: exposeFOW()]

                  #. .. code-block:: none

                        <!-- Expose FoW for selected tokens on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair")]

                  #. .. code:: de2

                        <!-- Expose FoW for indicated tokens on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair", "Westley, Count Rugen")]

                  #. .. code-block:: none

                        <!-- Expose FoW for indicated tokens, in a list delimited by a colon (":"), on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair", "Westley:Count Rugen", ":")])]

                  #. .. code-block:: none

                        <!-- Expose FoW for indicated tokens in a JSON array on the named map. -->

                  #. .. code:: de2

                        [h: exposeFOW("Pit of Despair",'["Westley", "Count Rugen"]', "json")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added tokens and delim parameters.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=exposeFOW&oldid=7456"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__
            -  `FoW </rptools/wiki/Category:FoW>`__

         --------------

         `FoW </rptools/wiki/Category:FoW>`__ >
         `FoW </rptools/wiki/Category:FoW>`__
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
            in </maptool/index.php?title=Special:UserLogin&returnto=exposeFOW>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/exposeFOW>`__
            -  `Discussion </maptool/index.php?title=Talk:exposeFOW&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/exposeFOW>`__
            -  `View
               source </maptool/index.php?title=exposeFOW&action=edit>`__
            -  `View
               history </maptool/index.php?title=exposeFOW&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/exposeFOW>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/exposeFOW>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=exposeFOW&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=exposeFOW&oldid=7456>`__
            -  `Page
               information </maptool/index.php?title=exposeFOW&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 13 August 2019, at 15:26.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
