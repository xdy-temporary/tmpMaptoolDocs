====================
replace - MapToolDoc
====================

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

   .. rubric:: replace
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

         .. rubric:: replace() Function
            :name: replace-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the string with the occurrences of a pattern
            replaced by the specified value. If the number of times to
            perform the replacement is not specified then all
            occurrences of the pattern are replaced. Pattern can be a
            `regular
            expression </rptools/wiki/Macros:regular_expression>`__.
            This means if the pattern string contains any regular
            expression special characters they must be escaped.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     replace(str, pattern, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     replace(str, pattern, value, times)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            **Example 1**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                            [r: replace("This is a test", " ", "-")]

                  #. .. code:: de1

                            [r: replace("This is a test", " ", "-", 2)]

            Returns:

            ::

                  This-is-a-test
                  This-is-a test

            | **Example 2**
            | This is useful for search+replace of any string you feed
              to ``replace()`` that might have regex codes in it like
              parenthesis:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                            [r: tString = "is (a) t"]

                  #. .. code:: de1

                            [r: replace("This is (a) test", "\\Q" + tString + "\\E", "-")]

            Returns:

            ::

                  This-est

            **Example 3**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                            [r: name = replace("wolph 5","(.*?) [0-9]+","\$1 42")]

            returns:

            ::

                  wolph 42

            The ``$`` normally means to match end-of-line, but only when
            it's at the end of the pattern. In this case, it's at the
            beginning of the pattern. And that means if the character
            immediately following is a digit (such as ``$1``), those
            characters are replaced by the source string matched by the
            corresponding set of parentheses in the regular expression.

            | **Example 4**
            | Note that multiple ``.*`` in the search string correspond
              with multiple ``$#``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                          [h:lastPath = [{"x":1,"y":0},{"x":1,"y":1},{"x":1,"y":2}]]

                  #. .. code:: de1

                          [r:result = replace(lastPath, '\\{"x":(.*?),"y":(.*?)\\}', '"X\$1Y\$2"')]

            returns:

            ["X1Y0","X1Y1","X1Y2"]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=replace&oldid=6009"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `String
               Function </rptools/wiki/Category:String_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `String
         Function </rptools/wiki/Category:String_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=replace>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/replace>`__
            -  `Discussion </maptool/index.php?title=Talk:replace&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/replace>`__
            -  `View
               source </maptool/index.php?title=replace&action=edit>`__
            -  `View
               history </maptool/index.php?title=replace&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/replace>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/replace>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=replace&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=replace&oldid=6009>`__
            -  `Page
               information </maptool/index.php?title=replace&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 4 October 2012, at 08:20.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
