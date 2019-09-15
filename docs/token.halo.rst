=======================
token.halo - MapToolDoc
=======================

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

   .. rubric:: token.halo
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

         The variable *token.halo* allows programmatic querying and
         setting of the token's **Halo**, a colored border that, if set,
         appears around the token. In the image below, the yellow border
         around the token is the token's halo.

         |Token-halo.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 Getting the Token Halo
                  Color <#Getting_the_Token_Halo_Color>`__
               -  `1.2 Setting the Token Halo
                  Color <#Setting_the_Token_Halo_Color>`__
               -  `1.3 Removing the Token
                  Halo <#Removing_the_Token_Halo>`__
               -  `1.4 Color Names and Standard
                  Colors <#Color_Names_and_Standard_Colors>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: Getting the Token Halo Color
            :name: getting-the-token-halo-color

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Halo color: [token.halo]

         Outputs the hexadecimal value for the token halo color. In the
         case of the example image above, it would output *#ffff00*.

         .. rubric:: Setting the Token Halo Color
            :name: setting-the-token-halo-color

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo = "red"]

         or

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo = #ff0000]

         Sets the color of the token.halo to red (or the hexadecimal
         value *#ff0000*).

         .. rubric:: Removing the Token Halo
            :name: removing-the-token-halo

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo="None"]

         .. rubric:: Color Names and Standard Colors
            :name: color-names-and-standard-colors

         The *token.halo* variable accepts the following named colors
         (if using a named color, enclose the value in quotes):

         -  Black
         -  Green
         -  Yellow
         -  Orange
         -  Red
         -  Blue
         -  Cyan
         -  DarkGray
         -  Magenta
         -  Pink
         -  White

         The variable will also accept any hexadecimal color value.
         Hexadecimal color values do not need to be enclosed in quotes.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=token.halo&oldid=2315"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=token.halo>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/token.halo>`__
            -  `Discussion </maptool/index.php?title=Talk:token.halo&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/token.halo>`__
            -  `View
               source </maptool/index.php?title=token.halo&action=edit>`__
            -  `View
               history </maptool/index.php?title=token.halo&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/token.halo>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/token.halo>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=token.halo&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=token.halo&oldid=2315>`__
            -  `Page
               information </maptool/index.php?title=token.halo&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 25 March 2009, at 13:54.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Token-halo.jpg| image:: /maptool/images/8/8f/Token-halo.jpg
   :width: 303px
   :height: 282px
   :target: /rptools/wiki/File:Token-halo.jpg
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
