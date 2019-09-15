=======================
tableImage - MapToolDoc
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

   .. rubric:: tableImage
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `tblImage </maptool/index.php?title=tblImage&redirect=no>`__\ )

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

            -  `1 tableImage() Function <#tableImage.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: tableImage() Function
            :name: tableimage-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Gets the image asset value from the specified
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
            If the row is not specified then the default
            `roll </maptool/index.php?title=Roll&action=edit&redlink=1>`__
            for the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            is used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     tableImage(name)

               #. .. code-block:: none

                     tableImage(name, row)

               #. .. code-block:: none

                     tableImage(name, row, size)

               #. .. code-block:: none

                     tblImage(name)

               #. .. code:: de2

                     tblImage(name, row)

               #. .. code-block:: none

                     tblImage(name, row, size)

         **Parameters**

         -  ``name`` - A string containing the name of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
         -  ``row`` - The row of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            that should have the image asset returned.
         -  ``size`` - The size the image asset returned should be. If
            the image is not square, this will be the size of the
            height.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:** Display a random image from
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            ``"tbl1"`` using default
            `roll </maptool/index.php?title=Roll&action=edit&redlink=1>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1")]'></image>

            **Example 1:** Display the first image from
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            ``"tbl1"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1", 1)]'></image>

            **Example 2:** Display one of the first four images, resized
            to ``40`` pixels tall, from ``"tbl1"``, chosed randomly:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1", "1d4", 40)]'></image>

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `table() </rptools/wiki/table>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=tableImage&oldid=6718"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Table
               Function </rptools/wiki/Category:Table_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Table
         Function </rptools/wiki/Category:Table_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=tableImage>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/tableImage>`__
            -  `Discussion </maptool/index.php?title=Talk:tableImage&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/tableImage>`__
            -  `View
               source </maptool/index.php?title=tableImage&action=edit>`__
            -  `View
               history </maptool/index.php?title=tableImage&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/tableImage>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/tableImage>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=tableImage&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=tableImage&oldid=6718>`__
            -  `Page
               information </maptool/index.php?title=tableImage&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 3 May 2016, at 12:59.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
