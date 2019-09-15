=======================
roll.count - MapToolDoc
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

   .. rubric:: roll.count
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

         The special variable *roll.count* holds the current iteration
         of current loop. It may be used with the following roll options
         for looping:

         -  `COUNT(): </rptools/wiki/Macros:Branching_and_Looping#COUNT_Option>`__
         -  `FOR(): </rptools/wiki/Macros:Branching_and_Looping#FOR_Option>`__
         -  `FOREACH(): </rptools/wiki/Macros:Branching_and_Looping#FOREACH_Option>`__
         -  `WHILE(): </rptools/wiki/Macros:Branching_and_Looping#WHILE_Option>`__

         The *roll.count* begins at 0.

         .. rubric:: Examples
            :name: examples

         **Simple Count**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [COUNT(5, "<br>"): "This is roll " + roll.count]

         *Outputs:*

         ::

            This is roll 0
            This is roll 1
            This is roll 2
            This is roll 3
            This is roll 4

         **Inner and Outer Loop**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r,foreach(item,"a,b,c,d,e,f",""),code: {

               #. .. code-block:: none

                       Loop: [r: roll.count] - [r: item] - 

               #. .. code-block:: none

                         [r,count(6): roll.count]<br>

               #. .. code-block:: none

                     }]

         *Outputs:*

         ::

             Loop: 0 - a - 0, 1, 2, 3, 4, 5 
             Loop: 1 - b - 0, 1, 2, 3, 4, 5 
             Loop: 2 - c - 0, 1, 2, 3, 4, 5 
             Loop: 3 - d - 0, 1, 2, 3, 4, 5 
             Loop: 4 - e - 0, 1, 2, 3, 4, 5 
             Loop: 5 - f - 0, 1, 2, 3, 4, 5 

         .. rubric:: Related Pages
            :name: related-pages

         -  `Branching and Looping
            Options </rptools/wiki/Macros:Branching_and_Looping>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=roll.count&oldid=7443"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Special
               Variable </rptools/wiki/Category:Special_Variable>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Special
         Variable </rptools/wiki/Category:Special_Variable>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=roll.count>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/roll.count>`__
            -  `Discussion </maptool/index.php?title=Talk:roll.count&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/roll.count>`__
            -  `View
               source </maptool/index.php?title=roll.count&action=edit>`__
            -  `View
               history </maptool/index.php?title=roll.count&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/roll.count>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/roll.count>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=roll.count&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=roll.count&oldid=7443>`__
            -  `Page
               information </maptool/index.php?title=roll.count&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 16 July 2019, at 12:10.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
