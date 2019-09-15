===================
assert - MapToolDoc
===================

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

   .. rubric:: assert
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

            -  `1 assert() Function <#assert.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Usage Notes <#Usage_Notes>`__
               -  `1.4 See Also <#See_Also>`__
               -  `1.5 Version Changes <#Version_Changes>`__

         .. rubric:: assert() Function
            :name: assert-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Halts execution and prints a custom error message if a
            condition is ``false``\ (``0``). Note that the error message
            will be displayed in chat even if the command itself is in a
            ``[H: ]`` block.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     assert(condition, message)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     assert(condition, message, prefix)

         **Parameters**

         -  ``condition`` - The test condition that must evaluate to
            ``true``\ (``1``) for the macro to continue.
         -  ``message`` - The custom error message that is presented if
            the macro is halted due to the ``false``\ (``0``) condition.
         -  ``prefix`` - Determines if the error message should have the
            message prefix ``"Macro defined error: "``. Defaults to
            ``true``\ (``1``), set to ``false``\ (``0``) if you do not
            wish your custom error message to have the message prefix.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Checks to see if a player is a GM, and if they are not halts
            execution of the macro and displays output.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: assert(isGM(),"This macro is for GM use only.",0)]

            Chat output (if player is not GM):
            ``This macro is for GM use only.``

            | 
            | Halts execution of the macro if ``var`` is a number. This
              is useful for making sure the variables you work with are
              the variable type you expect.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: assert(! isNumber(var), "The variable is a number.",1)]

            Chat output (if ``var`` is a number):
            ``Macro defined error: The variable is a number.``

            Bear in mind, ``isNumber(var)`` returns ``true``\ (``1``)
            when var is a number, but assert continues when condition is
            ``true``\ (``1``). Using ``! isNumber(var)`` inverts the
            boolean value.

            .. rubric:: Usage Notes
               :name: usage-notes

            When aborting a macro called from another macro (for
            example, a library token), all macros are aborted, not just
            the one executing.

            Since 1.5.0 you can change that behaviour by using
            macro.catchAssert.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isGM() </rptools/wiki/isGM>`__
            `isNumber() </rptools/wiki/isNumber>`__
            `abort() </rptools/wiki/abort>`__

            `macro.catchAssert </rptools/wiki/macro.catchAssert>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``prefix`` parameter option.
            -  **1.5.0** - catch an assert with macro.catchAssert

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=assert&oldid=7274"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Miscellaneous
         Function </rptools/wiki/Category:Miscellaneous_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=assert>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/assert>`__
            -  `Discussion </maptool/index.php?title=Talk:assert&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/assert>`__
            -  `View
               source </maptool/index.php?title=assert&action=edit>`__
            -  `View
               history </maptool/index.php?title=assert&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/assert>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/assert>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=assert&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=assert&oldid=7274>`__
            -  `Page
               information </maptool/index.php?title=assert&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 16 March 2019, at 23:55.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
