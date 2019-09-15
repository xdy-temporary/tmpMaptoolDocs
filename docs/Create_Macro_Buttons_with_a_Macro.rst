==============================================
Create Macro Buttons with a Macro - MapToolDoc
==============================================

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

   .. rubric:: Create Macro Buttons with a Macro
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

         This is the full macro code from the `Creating Macro Buttons
         Using a
         Macro </rptools/wiki/Creating_Macro_Buttons_Using_a_Macro>`__
         tutorial.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:powerSlot=macro.args]
                  [h:pname=getStrProp(eval("Power"+powerSlot),"powername")]
                  [h:use=getStrProp(eval("Power"+powerSlot),"usage")]
                   
                  [h:status=input(
                      "addButtons|Yes,No|Add Macro Buttons to your token?|RADIO|ORIENT=H SELECT=1"
                  )]
                  [h:abort(status)]
                   
                  [IF(addButtons==0),CODE:
                  {
                  [h,SWITCH(use),CODE:
                  case "at-will":
                  {
                    [bcolor="green"]
                    [fcolor="black"]
                    [group="1: Powers - At-Will"]
                    [grayout=0]
                  };
                  case "encounter":
                  {
                    [bcolor="red"]
                    [fcolor="white"]
                    [group="2: Powers - Encounter"]
                    [grayout=1]
                  };
                  case "daily":
                  {
                    [bcolor="black"]
                    [fcolor="white"]
                    [group="3: Powers - Daily"]
                    [grayout=1]
                  };
                  case "recharge":
                  {
                    [bcolor="blue"]
                    [fcolor="white"]
                    [group="3: Powers - Recharging"]
                    [grayout=1]
                  };]
                   
                  [h:macroProps="autoexec=true;"]
                  [h:macroProps=setStrProp(macroProps,"color",bcolor)]
                  [h:macroProps=setStrProp(macroProps,"fontColor",fcolor)]
                  [h:macroProps=setStrProp(macroProps,"group",group)]
                  [h:grayoutString=""]
                  [h,IF(grayout): grayoutString=encode("[h:setMacroProps(" + "'"
                                  +pname+ "'" + ",'color=gray;' " + ")]")]
                  [h:command=encode("[h:thisPower="+"'"+pname+"'"+"]")]
                  [h:command=command+encode("[h:index=getMacroIndexes(thisPower)]")]
                  [h:command=command+encode("[h:mProps=getMacroProps(index)]")]
                  [h:command=command+encode("[h:color=getStrProp(mProps,'color')]")]
                  [h:command=command+encode("[h:used=if(color=='gray', 0, 1)]")]
                  [h:command=command+encode("[h:abort(used)]")]
                  [h:command=command + encode("[MACRO('AttackMain@Lib:test'):thisPower]")]
                  [h:command=command+grayoutString]
                  [h:createMacro(pname, decode(command), macroProps)]
                  Buttons added.
                  };
                  {
                  No buttons added to token.
                  };]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&oldid=2628"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Create+Macro+Buttons+with+a+Macro>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Create_Macro_Buttons_with_a_Macro>`__
            -  `Discussion </maptool/index.php?title=Talk:Create_Macro_Buttons_with_a_Macro&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Create_Macro_Buttons_with_a_Macro>`__
            -  `View
               source </maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&action=edit>`__
            -  `View
               history </maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Create_Macro_Buttons_with_a_Macro>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Create_Macro_Buttons_with_a_Macro>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&oldid=2628>`__
            -  `Page
               information </maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 April 2009, at 14:04.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
