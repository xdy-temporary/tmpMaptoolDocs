================================================
Updating Macro Buttons Using Macros - MapToolDoc
================================================

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

   .. rubric:: Updating Macro Buttons Using Macros
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

         .. rubric:: Dynamically Updating a Token's Macro Buttons
            :name: dynamically-updating-a-tokens-macro-buttons

         Some times you want to modify what a
         `Token </rptools/wiki/Token>`__'s `macro
         button </rptools/wiki/Macro_Button>`__ from within a macro,
         this could be to visually represent a spell or power as having
         been used or even indicating that it is available for use.

         A quick note on some of these examples, before 1.3b51 it is
         only possible to have 2 levels deep of code: blocks, so some of
         the examples do things a little differently than you would if
         you could have multiple levels of code: blocks to avoid running
         into the problem. Also before 1.3b50 there is no way to get the
         index of the button that has been pressed, these tutorials show
         you how to "guess" the button that is pressed. As of 1.3b50 you
         can use the function
         `getMacroButtonIndex() </rptools/wiki/getMacroButtonIndex>`__
         to determine exactly which macro button has been clicked on the
         token.

         This tutorial is broken into several parts, although DnD4e is
         used to explain the concepts they are just as valid for any
         other system where you want to track if a skill has already
         been used or not.

         -  `Updating Macro Buttons Using a Macro (Prefix
            Method) </rptools/wiki/Updating_Macro_Buttons_Using_a_Macro_(Prefix_Method)>`__
         -  `Updating Macro Buttons Using a Macro (Group
            Method) </rptools/wiki/Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
         -  `Updating Macro Buttons Using a Macro (Label
            Method) </rptools/wiki/Updating_Macro_Buttons_Using_a_Macro_(Label_Method)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&oldid=5552"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Tutorial </rptools/wiki/Category:Tutorial>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Tutorial </rptools/wiki/Category:Tutorial>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Updating+Macro+Buttons+Using+Macros>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Updating_Macro_Buttons_Using_Macros>`__
            -  `Discussion </maptool/index.php?title=Talk:Updating_Macro_Buttons_Using_Macros&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Updating_Macro_Buttons_Using_Macros>`__
            -  `View
               source </maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&action=edit>`__
            -  `View
               history </maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Updating_Macro_Buttons_Using_Macros>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Updating_Macro_Buttons_Using_Macros>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&oldid=5552>`__
            -  `Page
               information </maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 5 July 2011, at 13:45.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
