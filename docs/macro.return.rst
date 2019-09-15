=========================
macro.return - MapToolDoc
=========================

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

   .. rubric:: macro.return
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

         The variable *macro.return* holds the value returned from a
         called macro to the calling macro. Other than *macro.return*, a
         called variable shares no other variables with the calling
         macro.

         .. rubric:: Examples
            :name: examples

         When a macro on a `library
         token </rptools/wiki/Token:library_token>`__ is called by
         another macro, the called macro may return a value to the
         called macro by assigning that value to the variable
         *macro.args*.

         .. rubric:: Calling Macro
            :name: calling-macro

         The macro below calls a macro called **getDamage** on the
         `library token </rptools/wiki/Token:library_token>`__
         "Lib:combat", passing the variable *damageDice* as an argument.
         It also sets

         +-----------------------------------+-----------------------------------+
         | Calling Macro                     | Called Macro                      |
         +===================================+===================================+
         | .. container::                    | .. container::                    |
         | mw-geshi mw-code mw-content-ltr   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |    .. container::                 |    .. container::                 |
         |    mtmacro source-mtmacro         |    mtmacro source-mtmacro         |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:damageDice="2d6"]  |             <!-- getDamage Macro  |
         |                                   | -->                               |
         |       #. .. code-block:: none            |                                   |
         |                                   |       #. .. code-block:: none            |
         |             [MACRO("getDamage@Lib |                                   |
         | :combat"):damageDice]             |             [h:returnData = ""]   |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:damageProperties=m |             [h:damageRoll = eval( |
         | acro.return]                      | macro.args) + 9]                  |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:varsFromStrProp(da |             [h:damageType = "pier |
         | mageProperties)]                  | cing"]                            |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |             You hit your target f |
         |                                   | or [r:damageRoll] damage!         |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:returnData=setStrP |
         |                                   | rop(returnData,"damType", damageT |
         |                                   | ype)]                             |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:returnData=setStrP |
         |                                   | rop(returnData,"damage", damageRo |
         |                                   | ll)]                              |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:macro.return=retur |
         |                                   | nData]                            |
         +-----------------------------------+-----------------------------------+

         In the example above, we assume that the **getDamage** macro
         was called by another macro (for example, a token macro) and
         has received some value in the form of *macro.args*. The
         statements in **getDamage** are executed, and the final
         statement assigns the value of returnData to the variable
         *macro.return*.

         When execution of the **getDamage** macro is complete and
         control is handed back to the calling macro, *macro.return* is
         also passed back to the calling macro, where it can be
         manipulated like any other variable.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macro.return&oldid=2286"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Special
               Variable </rptools/wiki/Category:Special_Variable>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Special
         Variable </rptools/wiki/Category:Special_Variable>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=macro.return>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/macro.return>`__
            -  `Discussion </maptool/index.php?title=Talk:macro.return&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/macro.return>`__
            -  `View
               source </maptool/index.php?title=macro.return&action=edit>`__
            -  `View
               history </maptool/index.php?title=macro.return&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/macro.return>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/macro.return>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=macro.return&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=macro.return&oldid=2286>`__
            -  `Page
               information </maptool/index.php?title=macro.return&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 25 March 2009, at 13:46.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
