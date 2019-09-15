===============================
HP and Health Bars - MapToolDoc
===============================

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

   .. rubric:: HP and Health Bars
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

         Updating hit points (or wounds, life points, or the like) using
         macros is a commonly requested macro procedure, and a very
         useful feature. When combined with MapTool's Bars feature
         (which can display health bars, ammo bars, and the like) it can
         be a simple and very cool way to keep an eye on how your
         character is doing.

         Setting up Health Bars and the macros that update them is easy
         too.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 The Bar <#The_Bar>`__
            -  `2 The Healing & Hurting
               Macro <#The_Healing_.26_Hurting_Macro>`__

               -  `2.1 HP and MaxHP <#HP_and_MaxHP>`__
               -  `2.2 Writing the Macro <#Writing_the_Macro>`__
               -  `2.3 Nonlethal damage <#Nonlethal_damage>`__

            -  `3 Links <#Links>`__

         .. rubric:: The Bar
            :name: the-bar

         To set up or change the various Bars you want in your game, you
         access the Bars dialog by selecting *Edit > Campaign
         Properties'*, and selecting the tab named **Bars**.

         You will see that by default, MapTool has one bar already set
         up - the Health Bar. A preview of this bar is shown in the
         lower portion of the Bars dialog (it will appear as a green bar
         on a black background). Grab the "Preview" slider and move it
         up and down - that's what the bar will look like as it is
         depleted.

         To see a bar on a Token, drag a token on the map, right-click
         on it, and select **Bars > Health.** A dialog will pop up that
         shows a slider, as well as a checkbox called "Hide." Uncheck
         the box, and hit **OK**, and the bar will appear over the
         token.

         We will not do anything fancy with the bar at this point -
         we'll leave it as is.

         .. rubric:: The Healing & Hurting Macro
            :name: the-healing-hurting-macro

         Bars can be altered by macros; each bar has a name, and when
         you need to refer to it in a macro, the variable you use is
         *bar.BarName*. So, for instance, the Health Bar - in macro
         speak - is *bar.Health*.

         We're going to create a short macro, in the Campaign window,
         that will adjust the hit points of a token, and adjust the
         Health Bar correspondingly. Before we can start, we need to
         make sure two properties exist.

         .. rubric:: HP and MaxHP
            :name: hp-and-maxhp

         Since the length of a health bar is calculated in our macro by
         dividing the current Hit Points by the Maximum Hit Points, we
         obviously need two Token Properties to represent these
         concepts. So, to do that, we edit the Campaign Properties to
         include two items: "HP" and *MaxHP* (you can use whatever name
         you like, but I like those).

         To put these properties in (assuming that you are using the
         default set of properties):

         #. Select **Edit > Campaign Properties**.
         #. In the Properties tab, select "Basic" in the left-hand list
            of property types.
         #. In the main text area, you will see a list of properties,
            including things like Strength, Dexterity, and so forth.
         #. Put your cursor in that text window, and add - at the bottom
            of the list - the property *MaxHP*.
         #. Click the "Update" button. The property list will be updated
            with the new *MaxHP* property.
         #. Click **OK**.

         You'll note that we didn't add any property for "current HP,"
         because the default properties already include that - it's
         called HP, and in the property list, it appears as *\*@HP*.

         Once you click OK, you can then double click on a token, and
         see the new property in the list of Token Properties. Make sure
         to put a number in that box (for instance, a token with all of
         its Hit Points, and a maximum of 25 hit points, should have the
         value 25 in both HP and MaxHP).

         .. rubric:: Writing the Macro
            :name: writing-the-macro

         Assuming you've successfully created the new token property
         *MaxHP*, we can move on to the macro itself. We're going to
         create a macro that pops up a small dialog, asking you for a
         number of hit points, and whether that many hit points is being
         lost or gained (damage or healing, in other words).

         #. In the Campaign macro window (if you don't see it, select
            **Window > Campaign**), right-click and select "Add New
            Macro."
         #. Right-click on the button labeled **(new)** and select
            **Edit**.
         #. In the macro editing dialog, label the new macro "Damage or
            Healing."
         #. At the bottom of the screen, check the box "Apply to
            Selected Tokens."
         #. In the "Options" tab, uncheck "Allow Players to Edit Macro"
            (if it is not already unchecked).
         #. Finally, go back to the "Details" tab, and in the main macro
            editing area, paste in the macro below.

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:status = input(
                  "hpChange|0|Number of Hit Points",
                  "dmgOrHealing|Damage,Healing|Is the character taking damage or being healed?|RADIO|SELECT=0")]
                  [h:abort(status)]
                   
                  [if(dmgOrHealing == 0),CODE:
                  {
                      [h:HP = HP - hpChange]
                      [h:bar.Health = HP / MaxHP]
                      [r:token.name] loses [r:hpChange] hit points.
                  };
                  {
                      [h:diff = MaxHP - HP]
                      [h:HP = min(HP+hpChange, MaxHP)]
                      [h:bar.Health = HP / MaxHP]
                      [r:token.name] is healed and gains  [r:min(diff,hpChange)] hit points. 
                  };]

         | 
         | After pasting that macro into the macro editing dialog, click
           **OK**, and you're all set. You should now be able to select
           a token (making sure the token has values for both HP and
           MaxHP - otherwise, you can get errors) and click the macro
           button, and you will be prompted to enter the amount of HP
           gained or lost. Once you hit "OK" on that dialog, the token's
           properties will be updated, and the health bar will update as
           well.

         .. rubric:: Nonlethal damage
            :name: nonlethal-damage

         This macro can be expanded to also allow for non-lethal damage
         fairly easily. To do so, add one more Property called *Nlthl*
         to track the token's nonlethal damage accumulation. Then the
         macro becomes:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:status = input(
                  "hpChange|0|Number of Hit Points",
                  "dmgOrHealing|Damage,Healing|Is the character taking damage or being healed?|RADIO|SELECT=0",
                  "lethalOrNo|Lethal,Nonlethal|Is the damage lethal?|RADIO|SELECT=0")]
                  [h:abort(status)]
                   
                  [if(dmgOrHealing == 0),CODE:
                  {
                      [if(lethalOrNo == 0),CODE:
                      {
                          [h:HP = HP - hpChange]
                          [h:bar.Health = (HP - Nlthl) / MaxHP]
                          [r:token.name] loses [r:hpChange] hit points.
                      };
                      {
                          [h:Nlthl = Nlthl + hpChange]
                          [h:bar.Health = (HP - Nlthl) / MaxHP]
                          [r:token.name] loses [r:hpChange] hit points.
                      };]
                  };
                  {
                      [h:diff = MaxHP - HP]
                      [h:HP = min(HP+hpChange, MaxHP)]
                      [h:Nlthl = max(Nlthl+hpChange, 0)]
                      [h:bar.Health = (HP - Nlthl) / MaxHP]
                      [r:token.name] is healed and gains  [r:min(diff,hpChange)] hit points. 
                  };]

         .. rubric:: Links
            :name: links

         #. `Fading Arc Health
            bar <http://forums.rptools.net/viewtopic.php?t=13493>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=HP_and_Health_Bars&oldid=4304"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=HP+and+Health+Bars>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/HP_and_Health_Bars>`__
            -  `Discussion </maptool/index.php?title=Talk:HP_and_Health_Bars&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/HP_and_Health_Bars>`__
            -  `View
               source </maptool/index.php?title=HP_and_Health_Bars&action=edit>`__
            -  `View
               history </maptool/index.php?title=HP_and_Health_Bars&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/HP_and_Health_Bars>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/HP_and_Health_Bars>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=HP_and_Health_Bars&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=HP_and_Health_Bars&oldid=4304>`__
            -  `Page
               information </maptool/index.php?title=HP_and_Health_Bars&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 23 June 2010, at 06:03.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
