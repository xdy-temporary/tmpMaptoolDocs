===================
return - MapToolDoc
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

   .. rubric:: return
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

            -  `1 return() Function <#return.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__

                  -  `1.2.1 Calling Macro <#Calling_Macro>`__
                  -  `1.2.2 Called Macro <#Called_Macro>`__
                  -  `1.2.3 Results <#Results>`__

               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: return() Function
            :name: return-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Is used to conditionally return from the execution of a
            macro like an abort, but not stopping further macro
            execution. Optionally also returning a value by
            automatically assigning
            `macro.return </rptools/wiki/macro.return>`__. If the first
            argument to ``return()`` is 0 then the return is happening.
            If the first argument to ``return()`` is non zero then the
            macro continues. The optional second argument of
            ``return()`` defines if there is a value that should be
            returned to a calling macro. Any other output is discarded
            when using ``return()``.
            Common uses for this function are

            -  Ending a macro with or without a return value to stop the
               further execution of the following lines in the current
               macro.
            -  The macro has conditions and based on these you want to
               return different values and not continue further in the
               current macro.

            If you prefer to display an error message when exiting the
            macro see the ```assert()`` </rptools/wiki/assert>`__
            function or if you want to abort the flow of overall macro
            execution (e.g. in case of an error) see the
            ```abort()`` </rptools/wiki/abort>`__ function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     return(continue, returnValue)

         **Parameters**

         -  ``continue`` - ``0`` if the return function should end the
            current macro, nonzero if it should not. So consistent to
            what the abort function is doing.
         -  ``returnValue`` - Optional. Any value passed in here will
            automatically be used as a return value (set to
            macro.return) and passed to the calling macro.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            The following example is about a called macro using the
            **return()** function to return a result to the calling
            macro. The calling macro could also be in a user defined
            function and then just used as a function in the caller
            macro.
            .. rubric:: Calling Macro
               :name: calling-macro

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- Call the testReturn library macro -->

                  #. .. code:: de1

                        [MACRO("testReturn@Lib:test"): ""]

                  #. .. code:: de1

                        Response is [r:macro.return].

            .. rubric:: Called Macro
               :name: called-macro

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- testReturn macro in Lib:test token -->

                  #. .. code:: de1

                        [h: return(0, "hello world")]

                  #. .. code:: de1

                        [h: "this will not be executed anymore"]

                  #. .. code:: de1

                        [h: macro.return = "this will not be set"]

            .. rubric:: Results
               :name: results

            TokenName: Response is hello world.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `assert() </rptools/wiki/assert>`__
            `abort() </rptools/wiki/abort>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.0** - introduced return function

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=return&oldid=7245"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=return>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/return>`__
            -  `Discussion </maptool/index.php?title=Talk:return&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/return>`__
            -  `View
               source </maptool/index.php?title=return&action=edit>`__
            -  `View
               history </maptool/index.php?title=return&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/return>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/return>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=return&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=return&oldid=7245>`__
            -  `Page
               information </maptool/index.php?title=return&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 10 March 2019, at 12:52.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
