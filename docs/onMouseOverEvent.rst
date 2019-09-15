=============================
onMouseOverEvent - MapToolDoc
=============================

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

   .. rubric:: onMouseOverEvent
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

         **This is a FAKE event**. You will need to create a macro and
         turn on some settings in Maptool to emulate this.

         This event can be simulated by turning on *"Show stat sheet on
         mouse over"* in the `MapTool
         Preferences </rptools/wiki/MapTool_Preferences#Tokens>`__:

         ::

               menu--> edit --> preferences --> Interactions --> 'Tokens' box: at the bottom --> check the checkbox

         And then creating a macro as a `campaign
         property </rptools/wiki/Introduction_to_Properties>`__ e.g.:

         ::

               *onMouseOverOnceVar:[macro("onMouseOver@lib:onMouseOver"):currentToken()]

         If you create a lib token ``lib:onMouseOver`` with the (self
         created) macro ``onMouseOver()`` then this macro will be called
         EVERY time you hover your mouse over a token.

         Note that this is extremely tricky and can result in system
         crashes or lock-ups if done incorrectly. The point is that the
         macro is called continuously when you hover over the token, so
         you have to take that into account when creating the macro.

         You can download a drop-in here
         `[1] <http://forums.rptools.net/viewtopic.php?f=46&t=18542>`__
         (if the link directs you to the 'forbidden' page then right
         mouse click on link and copy link location and paste that in
         the browser) that shows two methods that use this event. One
         method will run only once, this can be used e.g. to setup a
         token after you dragged it onto the map. The other method will
         run every time you hover over a token (but not continuously)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=onMouseOverEvent&oldid=5889"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Event </rptools/wiki/Category:Event>`__

         --------------

         `Review </rptools/wiki/Category:Review>`__ >
         `Stub </rptools/wiki/Category:Stub>`__ >
         `Event </rptools/wiki/Category:Event>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=onMouseOverEvent>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/onMouseOverEvent>`__
            -  `Discussion </maptool/index.php?title=Talk:onMouseOverEvent&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/onMouseOverEvent>`__
            -  `View
               source </maptool/index.php?title=onMouseOverEvent&action=edit>`__
            -  `View
               history </maptool/index.php?title=onMouseOverEvent&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/onMouseOverEvent>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/onMouseOverEvent>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=onMouseOverEvent&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=onMouseOverEvent&oldid=5889>`__
            -  `Page
               information </maptool/index.php?title=onMouseOverEvent&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 27 March 2012, at 10:27.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
