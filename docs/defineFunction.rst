===========================
defineFunction - MapToolDoc
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

   .. rubric:: defineFunction
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Could use examples of the
              ignoreOutput and newScope parameters.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 defineFunction()
               Function <#defineFunction.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: defineFunction() Function
            :name: definefunction-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Defines a user function that can be used anywhere that core
            functions can be used. A user defined function is a link to
            another macro. A special macro labeled
            `onCampaignLoad </rptools/wiki/onCampaignLoad>`__ is useful
            for defining functions upon the loading of your campaign.
            This because the function will be defined AFTER the macro
            has been run. In case of
            `onCampaignLoad </rptools/wiki/onCampaignLoad>`__, that
            macro is always run when the campaign is loaded. This saves
            you the hassle of manually requiring to run this macro to
            enable the definition.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     defineFunction(function, macro)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     defineFunction(function, macro, ignoreOutput)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     defineFunction(function, macro, ignoreOutput, newScope)

         **Parameters**

         -  ``function`` - The name of the user defined function to be
            defined.
         -  ``macro`` - The name and location of the macro that is
            called when the user defined function is used.
         -  ``ignoreOutput`` - If the defined function should ignore all
            output and only return the value of ``macro.return``,
            defaults to ``false``\ (``0``).
         -  ``newScope`` - If the defined function should create a new
            variable scope when executed, defaults to ``true``\ (``1``).
            A new variable scope means that the defined function can
            only read the variables of the macro that called it; if you
            do not create a new scope the defined function can read,
            update, and create variables in its parent's variable scope.
            Updating variables in the parent's scope includes
            over-writing any parameters that a parent might have stored
            within `arg() </rptools/wiki/arg>`__, if a user-defined
            function that does not create a new scope is called within
            another user-defined function.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: defineFunction("character.heal", "heal@Lib:Character")]

            Defines a function ``character.heal()`` which calls
            ``heal@Lib:Character`` when evoked. Note that in this case
            there must exist a function called "heal" on a token called
            "lib:Character". The advantage of using the prefix "lib:" on
            the token name is that it becomes a "lib:token" which is
            accessible from ANY map instead of only the map you happen
            to have active.

            Should you pass on any arguments e.g.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: character.heal("hello", "hi")]

            then these parameters can be accessed inside
            ``character.heal()`` by using

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: firstArg = arg(0)]

                  #. .. code:: de1

                        [h: theOtherOne = arg(1)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `oldFunction() </rptools/wiki/oldFunction>`__,
            `arg() </rptools/wiki/arg>`__,
            `argCount() </rptools/wiki/argCount>`__,

            `onCampaignLoad </rptools/wiki/onCampaignLoad>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b56** - Added ``ignoreOutput`` and ``newScope``
               parameter options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=defineFunction&oldid=7005"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Stub </rptools/wiki/Category:Stub>`__
            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `User Defined
               Function </rptools/wiki/Category:User_Defined_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `User
         Defined
         Function </rptools/wiki/Category:User_Defined_Function>`__
         `Review </rptools/wiki/Category:Review>`__ >
         `Stub </rptools/wiki/Category:Stub>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=defineFunction>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/defineFunction>`__
            -  `Discussion </maptool/index.php?title=Talk:defineFunction&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/defineFunction>`__
            -  `View
               source </maptool/index.php?title=defineFunction&action=edit>`__
            -  `View
               history </maptool/index.php?title=defineFunction&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/defineFunction>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/defineFunction>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=defineFunction&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=defineFunction&oldid=7005>`__
            -  `Page
               information </maptool/index.php?title=defineFunction&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 5 December 2018, at 18:09.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
