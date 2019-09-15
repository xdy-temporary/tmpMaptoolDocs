======================
evalMacro - MapToolDoc
======================

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

   .. rubric:: evalMacro
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `execMacro </maptool/index.php?title=execMacro&redirect=no>`__\ )

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

            -  `1 evalMacro() Function <#evalMacro.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: evalMacro() Function
            :name: evalmacro-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Evaluates and "executes" the macro in a string and returns
            the result. The string contains the same type of macro
            commands that you would put in a token macro with the
            exception that it can not contain slash commands.
            If you are performing rolls in the macro that create tool
            tips or use ``[e: ]`` then you will have to use either
            ``{ }`` or ``[r: ]`` to display the output otherwise you
            will get incorrect formatting.

            The **evalMacro()** function executes the macro in the same
            variable scope (i.e. the executed macro can read and alter
            variables from the current macro), where as
            `execMacro() </rptools/wiki/execMacro>`__ creates a new
            variable scope (i.e. the executed macro can neither read nor
            alter varaibles from the current macro).

            The advantage of this function over
            `eval() </rptools/wiki/eval>`__ is that with
            `eval() </rptools/wiki/eval>`__ you can only give a string
            as parameter that can be evaluated (e.g. ``"3+5"``), while
            with **evalMacro()** you can give anything as parameter but
            only the parts between ``[``\ brackets\ ``]`` will be
            evaluated. (e.g. ``"Your resulting roll is [r:1d10]"``)

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     evalMacro(macroString)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     execMacro(macroString)

         **Parameter**

         -  ``macroString`` - The string containing the macro script
            that is evaluated/executed.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: setNotes(evalMacro('[r,macro("CreateNotes@Lib:Notes"): ""]'))]

            Sets the Notes of a `Token </rptools/wiki/Token>`__ to the
            output of the ``CreateNotes`` macro located on the
            ``Lib:Notes`` `Library
            Token </rptools/wiki/Library_Token>`__.

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: evalMacro("[h: TestVar1 = 5][h: TestVar2 = 10][TestVar1+TestVar2]")]

            Returns ``15``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: TestVar3 = 10]

                  #. .. code:: de1

                        [h: TestVar4 = 20]

                  #. .. code:: de1

                        [r: evalMacro("[TestVar3+TestVar4]")]

            Returns ``30``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: TestVar3 = 15]

                  #. .. code:: de1

                        [h: TestVar4 = 30]

                  #. .. code:: de1

                        [h: evalMacro("[TestVar5 = TestVar3+TestVar4]")]

                  #. .. code:: de1

                        [TestVar5]

            Returns ``45``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: TestVar6 = 20]

                  #. .. code:: de1

                        [h: TestVar7 = 40]

                  #. .. code:: de1

                        [r: execMacro("[TestVar6+TestVar7]")]

            Prompts for the values of ``TestVar6`` and ``TestVar7``,
            then it returns the sum of those two values.

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: TestVar8 = 50]

                  #. .. code:: de1

                        [h: TestVar9 = 100]

                  #. .. code:: de1

                        [h: TestVar10 = 0]

                  #. .. code:: de1

                        [h: execMacro("[TestVar10 = TestVar8+TestVar9]")]

                  #. .. code:: de2

                        [TestVar10]

            Returns ``0``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: evalMacro("[h:roll=1d20]You roll [r:roll] and you [r:if(roll<10, 'hit', 'miss')] your target.")]

            Returns ``You roll 3 and you hit your target.``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `eval() </rptools/wiki/eval>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=evalMacro&oldid=6288"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=evalMacro>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/evalMacro>`__
            -  `Discussion </maptool/index.php?title=Talk:evalMacro&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/evalMacro>`__
            -  `View
               source </maptool/index.php?title=evalMacro&action=edit>`__
            -  `View
               history </maptool/index.php?title=evalMacro&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/evalMacro>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/evalMacro>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=evalMacro&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=evalMacro&oldid=6288>`__
            -  `Page
               information </maptool/index.php?title=evalMacro&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 17 May 2014, at 07:42.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
