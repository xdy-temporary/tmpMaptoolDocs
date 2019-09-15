=================================
Target a Visible NPC - MapToolDoc
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

   .. rubric:: Target a Visible NPC
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

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         This macro allows a player to pick-up a NPC among those he can
         currently see. Note that this is about the player's view and
         not the currently selected token's view. You may then store the
         target's name in the token's properties to ease further
         actions.

         Basically, the macro gets the list of all NPCs available (with
         `getNPCNames() </rptools/wiki/getNPCNames>`__) and the list of
         all visible tokens (with
         `getVisibleTokenNames() </rptools/wiki/getVisibleTokenNames>`__).
         Then, the intersection will provide visible NPCs.

         .. rubric:: Macro
            :name: macro

         **1.3b53+**

         --------------

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     /self 

               #. .. code:: de1

                     [h: lsVisibleNpc = json.intersection( getNPCNames("json"), getVisibleTokenNames("json") )]

               #. .. code:: de1

                      

               #. .. code:: de1

                     // Abort if no target found (intersection returned an empty list)

               #. .. code:: de2

                     [h: assert(json.length(lsVisibleNpc), "No visible NPC", 0)]

               #. .. code:: de1

                      

               #. .. code:: de1

                     // UI: popup a list for selection

               #. .. code:: de1

                     [h: input("index|"+json.toList(lsVisibleNpc)+"|My target is|LIST") ]

               #. .. code:: de1

                      

               #. .. code:: de2

                     // Retrieve the first element, so we only get the name (and not ["name"])

               #. .. code:: de1

                     [h: currentTgt = json.get(lsVisibleNpc, index) ]

               #. .. code:: de1

                      

               #. .. code:: de1

                     // Display message to be sure of what has just been done

               #. .. code:: de1

                     Current target : {currentTgt}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Target_a_Visible_NPC&oldid=4147"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Target+a+Visible+NPC>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Target_a_Visible_NPC>`__
            -  `Discussion </maptool/index.php?title=Talk:Target_a_Visible_NPC&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Target_a_Visible_NPC>`__
            -  `View
               source </maptool/index.php?title=Target_a_Visible_NPC&action=edit>`__
            -  `View
               history </maptool/index.php?title=Target_a_Visible_NPC&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Target_a_Visible_NPC>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Target_a_Visible_NPC>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Target_a_Visible_NPC&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Target_a_Visible_NPC&oldid=4147>`__
            -  `Page
               information </maptool/index.php?title=Target_a_Visible_NPC&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 21 February 2010, at 10:33.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
