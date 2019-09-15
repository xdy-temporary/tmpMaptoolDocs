============================
Roll Initiative - MapToolDoc
============================

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

   .. rubric:: Roll Initiative
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

         .. rubric:: Roll Initiative
            :name: roll-initiative

         This is a rather complex macro that will roll initiative for a
         group of tokens selected using a popular game system's rules.
         Specifically, the rules are:

         -  each token rolls 1d20 and adds a bonus (stored in the
            Initiative Property).
         -  ties go to the token with the higher bonus.
         -  groups of monsters all use the same roll -- or as
            implemented, tokens with the same image share the same roll.

         The code for this is below:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: initList = "booga=-1"];

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h, foreach(Selected, getSelected("json")), CODE:

               #. .. code-block:: none

                     {

               #. .. code:: de2

                        [switchToken(Selected)]

               #. .. code-block:: none

                      [SelectedGMName = getTokenImage()]

               #. .. code-block:: none

                        [arr = json.fromStrProp(initList)]

               #. .. code-block:: none

                        [if(json.contains(arr, SelectedGMName) != 0), CODE:

               #. .. code-block:: none

                        {

               #. .. code:: de2

                             [init = json.get(arr, SelectedGMName)]

               #. .. code-block:: none

                      };

               #. .. code-block:: none

                       {

               #. .. code-block:: none

                           [result = 1d20]

               #. .. code-block:: none

                             [init = result + getProperty("Initiative", Selected)]

               #. .. code:: de2

                             [tie = getProperty("Initiative", Selected) / 100]

               #. .. code-block:: none

                            [init = init + tie]

               #. .. code-block:: none

                          [initList = concat(initList, ";", SelectedGMName, "=", init)]

               #. .. code-block:: none

                       }]

               #. .. code-block:: none

                      

               #. .. code:: de2

                        [switchToken(Selected)]

               #. .. code-block:: none

                        [addToInitiative()]

               #. .. code-block:: none

                        [setInitiative(init)]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     [h: sortInitiative()]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h,foreach(Selected, getSelected("json")), CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         [switchToken(Selected)]

               #. .. code:: de2

                      [init = getInitiative()]

               #. .. code-block:: none

                      [init = floor(init)]

               #. .. code-block:: none

                      [setInitiative(init)]

               #. .. code-block:: none

                     }]

         The result is that if you have a party of 4 PCs all with
         different token images, and a group of 4 skeletons with the
         same token image, and 2 zombies with the same token image,
         which would be typical, and you select all the tokens and run
         this macro, your initiative list will be populated with all the
         tokens. The 4 skeletons will all have the same initiative
         result. The 2 zombies will both have the same initiative
         result. If there are any ties, tokens with the higher
         initiative bonus will be presented first.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Roll_Initiative&oldid=5815"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Roll+Initiative>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Roll_Initiative>`__
            -  `Discussion </maptool/index.php?title=Talk:Roll_Initiative&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Roll_Initiative>`__
            -  `View
               source </maptool/index.php?title=Roll_Initiative&action=edit>`__
            -  `View
               history </maptool/index.php?title=Roll_Initiative&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Roll_Initiative>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Roll_Initiative>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Roll_Initiative&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Roll_Initiative&oldid=5815>`__
            -  `Page
               information </maptool/index.php?title=Roll_Initiative&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 23 November 2011, at 13:44.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
