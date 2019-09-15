================
arg - MapToolDoc
================

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

   .. rubric:: arg
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

            -  `1 arg() Function <#arg.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: arg() Function
            :name: arg-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Is used to extract arguments that are passed to a macro when
            called as a user defined function.
            User functions are defined with the
            `defineFunction() </rptools/wiki/defineFunction>`__
            function. Once you have defined a function you can call it
            as you would call any of the existing functions, for example
            ``attackRoll(Strength, -1)``. The ``arg()`` function is used
            within the macro that is called to extract each of these
            arguments. The index of the first argument is 0.

            | 
            | The ```argCount()`` </rptools/wiki/argCount>`__ function
              is often used in conjunction with ``arg()`` to determine
              the number

            of arguments that have been passed to the user defined
            function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     arg(index)

         **Parameters**

         -  ``index`` - The index of the argument to return. Indexes
            begin at ``0``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Given a user defined function called ``attackRoll()`` which
            accepts two arguments, which are attribute value and
            bonus you could call it in the following way.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [attackRoll(12, -1)]

            Then inside the macro that implements the user defined
            function you can do the following.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: attr = arg(0)]

                  #. .. code-block:: none

                        [h: bonus = arg(1)]

                  #. .. code-block:: none

                        [r: 1d20 + floor(attr/2) + bonus]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() </rptools/wiki/defineFunction>`__,
            `isFunctionDefined() </rptools/wiki/isFunctionDefined>`__,
            `argCount() </rptools/wiki/argCount>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=arg&oldid=7190"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=arg>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/arg>`__
            -  `Discussion </maptool/index.php?title=Talk:arg&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/arg>`__
            -  `View
               source </maptool/index.php?title=arg&action=edit>`__
            -  `View
               history </maptool/index.php?title=arg&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/arg>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/arg>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=arg&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=arg&oldid=7190>`__
            -  `Page
               information </maptool/index.php?title=arg&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 6 March 2019, at 07:25.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
