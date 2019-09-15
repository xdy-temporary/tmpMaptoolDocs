===========================
onCampaignLoad - MapToolDoc
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

   .. rubric:: onCampaignLoad
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

            -  `1 onCampaignLoad Macro <#onCampaignLoad_Macro>`__

               -  `1.1 How to Create an onCampaignLoad
                  Macro <#How_to_Create_an_onCampaignLoad_Macro>`__
               -  `1.2 Limitations <#Limitations>`__
               -  `1.3 Example of Deferred Function
                  Calls <#Example_of_Deferred_Function_Calls>`__

         .. rubric:: onCampaignLoad Macro
            :name: oncampaignload-macro

         **• Introduced in version 1.3b51**

         A special macro that can be created on `library
         tokens </rptools/wiki/Library_Token>`__ to have macro code
         automatically execute when a campaign is loaded. A campaign is
         considered to have been loaded if it is opened via the File
         menu, or upon connecting to a server running that campaign. All
         output from an ``onCampaignLoad`` macro is discarded, when it
         is executed automatically.

         This special macro is ideally suited for loading your User
         Defined Functions (UDFs) via
         `defineFunction() </rptools/wiki/defineFunction>`__.

         When an onCampaignLoad macro is executed automatically, it is
         considered a `Trusted Macro </rptools/wiki/Trusted_Macro>`__.
         If you wish to use trusted functions within ``onCampaignLoad``
         and execute it manually (e.g. while developing macros), you
         will have to make sure that it follows all of the rules of
         `Trusted Macros </rptools/wiki/Trusted_Macro>`__.

         .. rubric:: How to Create an onCampaignLoad Macro
            :name: how-to-create-an-oncampaignload-macro

         You can create an ``onCampaignLoad`` macro on any `library
         token </rptools/wiki/Library_Token>`__; simply create a macro
         that is specifically named ``onCampaignLoad``.

         .. rubric:: Limitations
            :name: limitations

         -  Do not make changes within the ``onCampaignLoad`` macro to
            the library token it resides upon. This is not supported by
            MapTool. A duplicate lib token can/will appear and this
            will/can break stuff.
         -  Some macro functions may not work as expected if run in
            ``onCampaignLoad`` without deferring their execution by
            using the defer option of
            `execLink() </rptools/wiki/execLink>`__.

            -  `goto() </rptools/wiki/goto>`__,
               `setZoom() </rptools/wiki/setZoom>`__ and similar
               function calls should be placed in a separate macro to be
               called via `execLink() </rptools/wiki/execLink>`__

         .. rubric:: Example of Deferred Function Calls
            :name: example-of-deferred-function-calls

         Inside the ``onCampaignLoad`` macro place code like this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: link = macroLinkText("deferredCalls@"+getMacroLocation())]

               #. .. code:: de1

                     [h: execLink(link,1)]

         And in the deferredCalls() macro place the functions to be
         deferred.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: goto("2")]

               #. .. code:: de1

                     [h: setZoom(2)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=onCampaignLoad&oldid=7004"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Special Macro </rptools/wiki/Category:Special_Macro>`__
            -  `Event </rptools/wiki/Category:Event>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Special
         Macro </rptools/wiki/Category:Special_Macro>`__
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
            in </maptool/index.php?title=Special:UserLogin&returnto=onCampaignLoad>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/onCampaignLoad>`__
            -  `Discussion </maptool/index.php?title=Talk:onCampaignLoad&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/onCampaignLoad>`__
            -  `View
               source </maptool/index.php?title=onCampaignLoad&action=edit>`__
            -  `View
               history </maptool/index.php?title=onCampaignLoad&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/onCampaignLoad>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/onCampaignLoad>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=onCampaignLoad&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=onCampaignLoad&oldid=7004>`__
            -  `Page
               information </maptool/index.php?title=onCampaignLoad&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 5 December 2018, at 17:32.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
