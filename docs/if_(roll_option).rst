=============================
if (roll option) - MapToolDoc
=============================

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

   .. rubric:: if (roll option)
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

            -  `1 [if():] Roll Option <#.5Bif.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__

                  -  `1.1.1 -- Known Problems <#--_Known_Problems>`__

               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: [if():] Roll Option
            :name: if-roll-option

         .. container::

            \* **Introduced in version 1.3b46**

         Branches the flow of the roll as determined by the condition.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [if(condition): true_body]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [if(condition): true_body; false_body]

         **Parameters**

         -  ``condition`` - The condition/s to check to determine which
            roll (``true_body`` or ``false_body``) is executed, if any.
            The condition/s can only contain one level of nested
            parenthesis.
         -  ``true_body`` - The roll that is executed if the
            ``condition`` evaluates to ``true``\ (``1``). To use complex
            rolls in the ``true_body``, you must use the
            `[code():] </rptools/wiki/code_(roll_option)>`__ roll option
            in conjunction with this roll option.
         -  ``false_body`` - The roll that is executed if the
            ``condition`` evaluates to ``false``\ (``0``). If no
            ``false_body`` is given, there is no output if the
            ``condition`` evaluates to ``false``\ (``0``). To use
            complex rolls in the ``false_body``, you must use the
            `[code():] </rptools/wiki/code_(roll_option)>`__ roll option
            in conjunction with this roll option.

         | **Operators**
         | Operators are used to compare two variables, strings, literal
           numbers, expressions, or function outputs within a
           ``condition``.

         *Conditional Operators:*

         -  ``>`` - Greater than
         -  ``<`` - Less than
         -  ``>=`` - Greater than or equal to
         -  ``<=`` - Less than or equal to
         -  ``==`` - Equal to
         -  ``!=`` or ``ne`` - Not equal

         *Logical Operators:*

         -  ``&&`` - And
         -  ``||`` - Or

         *Boolean Operators:*

         -  ``true``
         -  ``false``
         -  ``!`` - Not

         It is important to note that the *Equal to* condition operator
         must be two equal signs (``==``). If you are checking for a
         text string, place quotes around the text.

         .. rubric:: -- Known Problems
            :name: known-problems

         -  **Number of () levels**

         The ``[if():]`` doesn't allow more than one level of ``()``.
         So,

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [R, if(((1))): "true";"false"]

         | will give an error.

         -  **Help! There are ' ' in the output**

         Note that currently

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [r,if(val == something),CODE:{Print something}]

         will produce extraneous single quotes in the output when the
         condition is false. The workaround for this is to add an empty
         block for the false side:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [r,if(val == something),CODE:{Print something};{}]

         .. rubric:: Example
            :name: example

         Sets the variable ``newVal`` to ``12*12`` if the variable
         ``val`` equals ``12``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:val=12]

               #. .. code:: de1

                     [h,if(val == 12): newVal=12*12]

               #. .. code:: de1

                     New Value = [r: newVal]

         Returns ``New Value = 144``

         Example with logical operators:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h,if((val > 12 && val < 24) || val == 5): val=1 ; val=0]

         These examples perform the same function. If ``val`` is not a
         number, make ``val`` equal ``0``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h, if (! isNumber(val)): val = 0)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h, if (isNumber(val) == 0): val = 0)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h, if (isNumber(val) == false): val = 0)]

         The following will generate an error:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h,if(getName(getSelected()) == "Giant Rat"): val=1]  --- ERROR, too many parenthesis on condition!

               #. .. code:: de1

                     [h,if(getName() == "Giant Rat")): val=1] ---  This is OK.

         .. rubric:: See Also
            :name: see-also

         `if() </rptools/wiki/if>`__,
         `isNumber() </rptools/wiki/isNumber>`__,
         `[code():] </rptools/wiki/code_(roll_option)>`__, `Introduction
         to Macro
         Branching </rptools/wiki/Introduction_to_Macro_Branching>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=if_(roll_option)&oldid=6025"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Roll Option </rptools/wiki/Category:Roll_Option>`__
            -  `Branching Roll
               Option </rptools/wiki/Category:Branching_Roll_Option>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__ > `Branching
         Roll Option </rptools/wiki/Category:Branching_Roll_Option>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=if+%28roll+option%29>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/if_(roll_option)>`__
            -  `Discussion </maptool/index.php?title=Talk:if_(roll_option)&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/if_(roll_option)>`__
            -  `View
               source </maptool/index.php?title=if_(roll_option)&action=edit>`__
            -  `View
               history </maptool/index.php?title=if_(roll_option)&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/if_(roll_option)>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/if_(roll_option)>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=if_(roll_option)&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=if_(roll_option)&oldid=6025>`__
            -  `Page
               information </maptool/index.php?title=if_(roll_option)&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 18 October 2012, at 12:22.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
