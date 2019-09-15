========================
Trim Number - MapToolDoc
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

   .. rubric:: Trim Number
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

         | **Requires MapTool 1.3b56**
         | The following is a user defined function that allows you to
           trim any trailing zeros from a floating point number(a number
           with decimal places). It also allows you to truncate the
           decimal places to a certain length and round any truncated
           decimal places in a certain direction.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number, length)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number, length, direction)

         **Parameters:**

         -  ``number`` - The number to be trimmed.
         -  ``length`` - How many decimal places the trimmed number
            should retain, defaults to ``10``.
         -  ``direction`` - A string containing the direction that any
            truncated decimals placed should be rounded it. Accepts
            ``"up"``, ``"u"``, ``"down"``, and ``"d"``, defaults to
            rounding to the nearest.

         .. rubric:: Macros
            :name: macros

         Place the following macros on the same library token(or on
         different library tokens if you're know what you're doing and
         what to change).

         --------------

         **onCampaignLoad**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [defineFunction("trimNumber", "trimNumber@this", 1)]

         --------------

         --------------

         **trimNumber**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [assert(argCount() != 0, "trimNumber() requires at least one parameter.")]
                  [assert(argCount() <= 3, "trimNumber() accepts a maximum of three parameters.")]
                  [NumberToTrim = arg(0)]
                  <!-- Set truncation depth -->
                  [if(argCount() >= 2), code:
                  {
                      [TruncationDepth = power(10, arg(1))]
                  };{
                      [TruncationDepth = power(10, 10)]
                  }]
                  <!-- Set rounding method -->
                  [if(argCount() == 3), code:
                  {
                      [RoundingMethod = substring(arg(2), 0 , 1)]
                  };{
                      [RoundingMethod = 0]
                  }]
                  <!-- Perform trim -->
                  [switch(RoundingMethod):
                      case "u": NumberToTrim = ceiling(NumberToTrim*TruncationDepth)/TruncationDepth;
                      case "d": NumberToTrim = floor(NumberToTrim*TruncationDepth)/TruncationDepth;
                      default: NumberToTrim = round(NumberToTrim*TruncationDepth)/TruncationDepth
                  ]
                  [macro.return = NumberToTrim]

         --------------

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.125000)]

         Returns ``1.125``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.125000, 2)]

         Returns ``1.13``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.124000, 2)]

         Returns ``1.12``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.123000, 2, "up")]

         Returns ``1.13``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.128000, 2, "down")]

         Returns ``1.12``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Trim_Number&oldid=3355"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Trim+Number>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Trim_Number>`__
            -  `Discussion </maptool/index.php?title=Talk:Trim_Number&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Trim_Number>`__
            -  `View
               source </maptool/index.php?title=Trim_Number&action=edit>`__
            -  `View
               history </maptool/index.php?title=Trim_Number&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Trim_Number>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Trim_Number>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Trim_Number&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Trim_Number&oldid=3355>`__
            -  `Page
               information </maptool/index.php?title=Trim_Number&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 11 May 2009, at 23:49.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
