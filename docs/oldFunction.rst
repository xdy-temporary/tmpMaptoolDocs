========================
oldFunction - MapToolDoc
========================

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

   .. rubric:: oldFunction
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

            -  `1 oldFunction()
               Function <#oldFunction.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: oldFunction() Function
            :name: oldfunction-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            If a user-defined function redefines a standard MapTool
            function or another user-defined function -- for instance, a
            user defines a function called ``eval()``, redefining the
            standard MapTool `eval() </rptools/wiki/eval>`__ --
            **oldFunction()** can be used in the user-defined function
            to call the original function. When a user-defined function
            redefines an existing function, it keeps track of the
            function that it redefined. Due to this tracking, it is
            possible to redefine a function multiple times and
            **oldFunction()** will always reference the previous
            function in the chain. **Note:** Do not rely on a specific
            order in the function chain unless you are sure that the
            functions will be redefined in that order. Calls to
            `defineFunction() </rptools/wiki/defineFunction>`__ within
            `onCampaignLoad </rptools/wiki/onCampaignLoad>`__ macros on
            different `Library Tokens </rptools/wiki/Library_Token>`__
            are not executed in any standard order.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     oldFunction(SPECIAL)

         **Parameter**

         -  ``SPECIAL`` - oldFunction supports the same parameters as
            the function that it is referencing.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Within a user-defined function named ``eval()``,
            **oldFunction()** is used to call the standard MapTool
            `eval() </rptools/wiki/eval>`__ function.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [h, if ( arg(0) == 0 ), code:
                     {
                         [h: macro.return = 0]
                     };{
                         [h: macro.return = oldFunction( arg(0) ) ]
                     }]

            By having access to the original function definition, this
            example is able to provide custom or standard return values
            when called.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() </rptools/wiki/defineFunction>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=oldFunction&oldid=3158"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

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
            in </maptool/index.php?title=Special:UserLogin&returnto=oldFunction>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/oldFunction>`__
            -  `Discussion </maptool/index.php?title=Talk:oldFunction&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/oldFunction>`__
            -  `View
               source </maptool/index.php?title=oldFunction&action=edit>`__
            -  `View
               history </maptool/index.php?title=oldFunction&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/oldFunction>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/oldFunction>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=oldFunction&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=oldFunction&oldid=3158>`__
            -  `Page
               information </maptool/index.php?title=oldFunction&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 17 April 2009, at 01:35.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
