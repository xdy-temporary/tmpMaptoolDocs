===============================
Macros:Roll:output - MapToolDoc
===============================

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

   .. rubric:: Macros:Roll:output
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

            -  `1 Roll Visibility Options <#Roll_Visibility_Options>`__

               -  `1.1 Output Visibility <#Output_Visibility>`__
               -  `1.2 Tooltip Visibility <#Tooltip_Visibility>`__

            -  `2 Related Pages <#Related_Pages>`__

         .. rubric:: Roll Visibility Options
            :name: roll-visibility-options

         .. rubric:: Output Visibility
            :name: output-visibility

         These roll options control who is able to see the result of a
         given roll.

         -  **[s: ]**, **[self: ]** makes the roll visible only to the
            player who made the roll.
         -  **[g: ]**, **[gm: ]** makes the roll visible only to GMs.
         -  **[w("name"): ]**, **[whisper("name"): ]** makes the roll
            visible to the selected player.

         These roll options can be combined to make a roll visible to
         multiple people. If none of these options are used, output is
         visible to everyone.

         **[w(): ]** can also take more than one player name as an
         argument:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [w("Fred", "Joe"): d20]

         It can also take a JSON list containing player names:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: names = json.fromList("Fred, Joe")]

               #. .. code:: de1

                     [w(names): d20]

         If a chat message would appear empty because everything in it
         is hidden from the player, the message is not displayed.

         .. rubric:: Tooltip Visibility
            :name: tooltip-visibility

         These options control who can see the tooltip showing detailed
         roll output. If the roll doesn't have a tooltip, these have no
         effect.

         -  **[st: ]**, **[selftt: ]** makes the tooltip visible only to
            the player who made the roll.
         -  **[gt: ]**, **[gmtt: ]** makes the tooltip visible only to
            GMs.

         These options can be combined with each other and with the
         other output options. If neither of these options are used, the
         tooltip is visible to everyone.

         .. rubric:: Related Pages
            :name: related-pages

         -  `Roll Types and Options </rptools/wiki/Macros:Roll:types>`__
         -  `Branching and Looping Roll
            Options </rptools/wiki/Macros:Branching_and_Looping>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Macros:Roll:output&oldid=3948"

      .. container:: catlinks catlinks-allhidden
         :name: catlinks

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Macros%3ARoll%3Aoutput>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Macros:Roll:output>`__
            -  `Discussion </maptool/index.php?title=Talk:Macros:Roll:output&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Macros:Roll:output>`__
            -  `View
               source </maptool/index.php?title=Macros:Roll:output&action=edit>`__
            -  `View
               history </maptool/index.php?title=Macros:Roll:output&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Macros:Roll:output>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Macros:Roll:output>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Macros:Roll:output&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Macros:Roll:output&oldid=3948>`__
            -  `Page
               information </maptool/index.php?title=Macros:Roll:output&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 23 September 2009, at 06:30.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
