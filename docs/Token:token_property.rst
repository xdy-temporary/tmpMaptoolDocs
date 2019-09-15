===========================
Token Property - MapToolDoc
===========================

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

   .. rubric:: Token Property
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected from\ `Token:token
         property </maptool/index.php?title=Token:token_property&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         A *token property* is a variable (string or numeric) that
         resides on a particular `token </rptools/wiki/Token:token>`__
         within MapTool, and may be called upon or evaluated by macros.

         Token properties are tailored to fit each individual campaign
         file and the macros contained in that campaign. Multiple sets
         of token properties can be created (allowing them to be applied
         to different classes of token - for example, PC tokens versus
         NPC tokens). These multiple sets are called `token property
         types </rptools/wiki/Token:token_property_type>`__.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Default Token
               Properties <#Default_Token_Properties>`__
            -  `2 Setting Campaign
               Properties <#Setting_Campaign_Properties>`__

               -  `2.1 Token Property Format <#Token_Property_Format>`__
               -  `2.2 Example Token
                  Property <#Example_Token_Property>`__
               -  `2.3 Controlling Token Property
                  Display <#Controlling_Token_Property_Display>`__

         .. rubric:: Default Token Properties
            :name: default-token-properties

         By default, MapTool has the following set of token properties.

         ::

            Strength (Str)
            Dexterity (Dex)
            Constitution (Con)
            Intelligence (Int)
            Wisdom (Wis)
            Charisma (Char)
            *@HP
            *@AC
            Defense (Def)
            Movement (Mov)
            *Elevation (Elv)
            Description (Des)

         .. rubric:: Setting Campaign Properties
            :name: setting-campaign-properties

         Campaign properties are edited using the Campaign Properties
         dialog, which is found under **Edit -> Campaign Properties** on
         the MapTool menu. They can be directly edited in the Campaign
         Properties dialog, or pasted in from a text editor of choice.

         .. rubric:: Token Property Format
            :name: token-property-format

         The format for all token properties.

         ::

            #*@PropertyName(ShortName):default value

         .. rubric:: Example Token Property
            :name: example-token-property

         ::

            *@HealingSurges(Surges):9

         Will display **Surges: 9** in the statsheet.

         .. rubric:: Controlling Token Property Display
            :name: controlling-token-property-display

         There are three "switches" (shown in the format string above)
         that control how campaign properties are displayed in the popup
         *statsheet* when the user hovers his mouse over a token:

         \* - Displays the property on the *statsheet*

         @ - Property will be visible only to the owner of that token

         # - Property will be visible only to the GM

         Note that the **\*** switch is essential for the property to be
         displayed on the statsheet; the **@** and **#** are optional
         modifiers to that display. If no switch is set in the property
         string, the property will be present on the token and
         accessible to macros but will *not* be displayed in the popup
         statsheet.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Token_Property&oldid=2240"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Token </rptools/wiki/Category:Token>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Token </rptools/wiki/Category:Token>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Token+Property>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Token_Property>`__
            -  `Discussion </maptool/index.php?title=Talk:Token_Property&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Token_Property>`__
            -  `View
               source </maptool/index.php?title=Token_Property&action=edit>`__
            -  `View
               history </maptool/index.php?title=Token_Property&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Token_Property>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Token_Property>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Token_Property&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Token_Property&oldid=2240>`__
            -  `Page
               information </maptool/index.php?title=Token_Property&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `日本語 <http://lmwcs.com/rptools/wiki/Token_Property/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 25 March 2009, at 12:40.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
