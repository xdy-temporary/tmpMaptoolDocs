===================
foobar - MapToolDoc
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

   .. rubric:: foobar
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

         The *bar.[bar_name]* variable permits the getting and setting
         of the `token
         bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
         value (and the corresponding image displayed on the token)
         programmatically. Token bars are one, two, or multi-image
         graphical elements displayed on a token that are used
         (typically) to visually indicate the status of consumable or
         expendable items or character traits (such as Hit Points,
         Ammunition, Health, or the like).

         Bars, like `token states </rptools/wiki/Token:state>`__, are
         configured via the Campaign Properties dialog and are specific
         to the campaign in which they exist. In the screenshot shown
         below, the green-on-black line across the top of the token is a
         token bar.

         |Bar-example.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Usage <#Usage>`__
            -  `2 Examples <#Examples>`__
            -  `3 Notes <#Notes>`__
            -  `4 Related Pages <#Related_Pages>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [bar.[bar_name] = value]

         Sets the value of the token bar named *bar_name* to the desired
         value. *bar_name* is set when the bar is created, and may be
         any name, provided it contains no spaces or special characters
         except the underscore. *Value* must be a number between 0 and
         1.

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: HP = HP - DamageTaken]

               #. .. code:: de1

                     [h: bar.Health = HP / MaxHP]

         Sets the value of *bar.Health* to the result of *HP / MaxHP*.

         .. rubric:: Notes
            :name: notes

         Two functions,
         `setBar() </rptools/wiki/Macros:Functions:setBar>`__ and
         `getBar() </rptools/wiki/Macros:Functions:getBar>`__ also exist
         to get and set the value of the token bar.

         .. rubric:: Related Pages
            :name: related-pages

         -  `List of Special
            Variables </rptools/wiki/Macros:Variables:list_of_special_variables>`__
         -  `Token Bar
            Functions </rptools/wiki/Macros:Functions:list_of_functions_by_area#Token_Bars>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bar.name&oldid=2385"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=bar.name>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/bar.name>`__
            -  `Discussion </maptool/index.php?title=Talk:bar.name&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/bar.name>`__
            -  `View
               source </maptool/index.php?title=bar.name&action=edit>`__
            -  `View
               history </maptool/index.php?title=bar.name&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/bar.name>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/bar.name>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=bar.name&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=bar.name&oldid=2385>`__
            -  `Page
               information </maptool/index.php?title=bar.name&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 27 March 2009, at 20:00.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Bar-example.jpg| image:: /maptool/images/a/a8/Bar-example.jpg
   :width: 328px
   :height: 235px
   :target: /rptools/wiki/File:Bar-example.jpg
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
