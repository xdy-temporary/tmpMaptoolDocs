=================================
More Roll Initiative - MapToolDoc
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

   .. rubric:: More Roll Initiative
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

            -  `1 Roll Initiative with
               Hold <#Roll_Initiative_with_Hold>`__

               -  `1.1 Macro
                  "onCommandLoad" <#Macro_.22onCommandLoad.22>`__
               -  `1.2 Macro "Roll_Init" <#Macro_.22Roll_Init.22>`__
               -  `1.3 Macro
                  "roll_init_core" <#Macro_.22roll_init_core.22>`__
               -  `1.4 Commentary <#Commentary>`__

         .. rubric:: Roll Initiative with Hold
            :name: roll-initiative-with-hold

         This example contains three different macros. Together, they
         will roll initiative for a group of tokens selected using a
         somewhat popular game system's rules. Specifically, the rules
         are:

         -  each token gets a card
         -  tokens that are on hold do not get a card, but use their
            card from the previous turn
         -  groups of monsters all use the same roll -- or as
            implemented, tokens with the same image share the same roll.
         -  tokens that are dead or incapacitated (defined by having one
            of those states) do not get a card.

         The code needs to be in three different macros because it nests
         more than two levels of CODE. The "onCampaignLoad" macro is
         used to set up some user defined function names. The main
         function can be called from the chat interface with the command
         "[dealinit()]", and the macro called by dealinit() then calls
         another macro. All of these macros should be defined in the
         same library token.

         .. rubric:: Macro "onCommandLoad"
            :name: macro-oncommandload

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: defineFunction("dealinit","Roll_Init@this")]
                  [h: defineFunction("coreinit","roll_init_core@this")]

         .. rubric:: Macro "Roll_Init"
            :name: macro-roll_init

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: initList = "booga=-1"];
                  [h: cardList = "-1"];
                  [h: rndnum = getInitiativeRound()]
                  [h: cntSize = initiativeSize()]
                  [h: setCurrentInitiative(cntSize + 1)]
                   
                  [h,foreach(Selected, getSelected("json")), CODE:
                  {
                    [h: switchToken(Selected)]
                      [h: init = getInitiative()]
                   
                      [h, if(getInitiativeHold() != 1), CODE:
                    {
                        [h: removeFromInitiative(init)]
                          [h: SelectedGMName = getTokenImage()]
                   
                          [h: init = coreinit(SelectedGMName, cardList, initList)]
                   
                          [h: arr = json.fromStrProp(initList)]
                          [h, if(json.contains(arr, SelectedGMName) == 0): initList = concat(initList, ";", SelectedGMName, "=", init)]
                          [h: switchToken(Selected)]
                          [h: addToInitiative()]
                          [h: setInitiative(init)]
                      };
                      {
                        [h: removeFromInitiative(init)]
                        [h: switchToken(Selected)]
                        [h: addToInitiative()]
                        [h: setInitiative(init)]
                        [h: setInitiativeHold(1)]
                    };]
                   
                      [h,if(getState("Dead") || getState("Incapacitated")), CODE:
                    {
                        [h: removeFromInitiative(init)] 
                      };
                      {
                        [h: cardList = concat(cardList,  ";", init)]
                    };]
                  }]
                   
                  [h: sortInitiative()]
                  [h: setCurrentInitiative(0)]
                   
                  [h: setInitiativeRound(rndnum + 1)]
                  [h:abort(0)]

         cardList is used to keep track of the cards that have been
         dealt.

         initList keeps track of tokens with the same image. Tokens that
         are on hold are never put in the initList, and keep their old
         status.

         .. rubric:: Macro "roll_init_core"
            :name: macro-roll_init_core

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: SelectedGMName = arg(0)]
                  [h: cardList = arg(1)]
                  [h: initList = arg(2)]
                   
                  [h: arr = json.fromStrProp(initList)]
                  [h, if(json.contains(arr, SelectedGMName) != 0), CODE:
                  {
                      [h: init = json.get(arr, SelectedGMName)]
                  };
                  {
                      [h: init = 1d54]
                      [h: foo = json.fromStrProp(cardList)]
                      [h, while(json.contains(foo, init) != 0), CODE:
                      {
                          [h: init =1d54]
                      }]
                  };]
                   
                  [h: macro.return = init]

         This macro draws a unique card from a deck of 54 cards. There's
         likely a better way to implement drawing from a deck, but this
         is simple and works fast enough.

         .. rubric:: Commentary
            :name: commentary

         The result is that if you have a party of 4 PCs all with
         different token images, and a group of 4 skeletons with the
         same token image, and 2 zombies with the same token image,
         which would be typical, and you select all the tokens and run
         this macro, your initiative list will be populated with all the
         tokens. The 4 skeletons will all have the same initiative
         result. The 2 zombies will both have the same initiative
         result. If any of the tokens are on hold, they'll keep their
         last initiative, but other tokens with the same image will
         share a different initiative.

         This code was based on the `Roll
         Initiative </rptools/wiki/Roll_Initiative>`__ sample.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=More_Roll_Initiative&oldid=4682"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=More+Roll+Initiative>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/More_Roll_Initiative>`__
            -  `Discussion </maptool/index.php?title=Talk:More_Roll_Initiative&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/More_Roll_Initiative>`__
            -  `View
               source </maptool/index.php?title=More_Roll_Initiative&action=edit>`__
            -  `View
               history </maptool/index.php?title=More_Roll_Initiative&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/More_Roll_Initiative>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/More_Roll_Initiative>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=More_Roll_Initiative&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=More_Roll_Initiative&oldid=4682>`__
            -  `Page
               information </maptool/index.php?title=More_Roll_Initiative&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 12 October 2010, at 02:53.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
