================================================================
Updating Macro Buttons Using a Macro (Group Method) - MapToolDoc
================================================================

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

   .. rubric:: Updating Macro Buttons Using a Macro (Group Method)
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

            -  `1 Updating color of our macro buttons using DnD4e as an
               example <#Updating_color_of_our_macro_buttons_using_DnD4e_as_an_example>`__

               -  `1.1 Short Rest, resetting color of buttons in the
                  "Encounter Powers"
                  group <#Short_Rest.2C_resetting_color_of_buttons_in_the_.22Encounter_Powers.22_group>`__
               -  `1.2 Extended Rest, resetting color of buttons
                  starting with "Encounter Powers" or "Daily
                  Powers" <#Extended_Rest.2C_resetting_color_of_buttons_starting_with_.22Encounter_Powers.22_or_.22Daily_Powers.22>`__
               -  `1.3 Using Powers, or getting the
                  blues... <#Using_Powers.2C_or_getting_the_blues...>`__
               -  `1.4 Multiple Power Buttons with the same
                  name <#Multiple_Power_Buttons_with_the_same_name>`__
               -  `1.5 Sorry Sir/Madam, you have already used
                  that! <#Sorry_Sir.2FMadam.2C_you_have_already_used_that.21>`__

         .. rubric:: Updating color of our macro buttons using DnD4e as
            an example
            :name: updating-color-of-our-macro-buttons-using-dnd4e-as-an-example

         For an example I will use DnD4e powers, when a power is used it
         will then update the button to show this. Although this is
         example is for DnD4e the technique is applicable for many other
         systems.

         Lets assume that you have a macro groups named "Daily Powers"
         and "Encounter Powers" where we place all of our powers, and we
         want to set the color of the `macro
         button </rptools/wiki/Macro_Button>`__ to blue if the power has
         been used. If you want another way to do this without using
         different groups see `Tracking Used DnD 4e Powers (Macro Prefix
         Method) </rptools/wiki/Tutorials:Macros:UpdatingMacroButtons:DnD4ePowersPrefix>`__

         | 

         **Version update:** This tutorial was written before 1.3b50. As
         of 1.3b50 you can use
         `getMacroButtonIndex </rptools/wiki/Macros:Functions:getMacroButtonIndex>`__
         to determine the index of the button that was pressed instead
         of setting/getting the properties of the button by name you can
         use the index of the button in place of the name, this way you
         will not run the risk of updating buttons with the same name.

         | 

         .. rubric:: Short Rest, resetting color of buttons in the
            "Encounter Powers" group
            :name: short-rest-resetting-color-of-buttons-in-the-encounter-powers-group

         So first we will create a `macro
         button </rptools/wiki/Macro_Button>`__ called "Short Rest", for
         this tutorial I will assume you just create it as a `campaign
         macro </rptools/wiki/Introduction_to_Macro_Writing#Campaign_Macros>`__
         --just remember to check the `Apply to Selected
         Tokens </maptool/index.php?title=Macros:Apply_to_Selected_Tokens&action=edit&redlink=1>`__
         check mark-- you can just as easily create these as macros in
         `library token </rptools/wiki/Token:library_token>`__ macros
         and call them from from `macro
         buttons </rptools/wiki/Macro_Button>`__ on your
         `tokens </rptools/wiki/Token>`__.

         |ShortRest1MacroButton.png|

         So create the "Short Rest" `macro
         button </rptools/wiki/Macro_Button>`__ and copy the following
         code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

               #. .. code:: de1

                      

               #. .. code:: de1

                     [h,foreach(macro, getMacros()), code: {

               #. .. code:: de1

                       <!-- 

               #. .. code:: de2

                         == each label can appear more than once (i.e. more than one

               #. .. code:: de1

                         == button with same label, so we need to get all the button

               #. .. code:: de1

                         == indexes for a label

               #. .. code:: de1

                       -->

               #. .. code:: de1

                      

               #. .. code:: de2

                       [h,foreach(index, getMacroIndexes(macro)), code: {

               #. .. code:: de1

                         [props = getMacroProps(index)]

               #. .. code:: de1

                         [isBlue = if(getStrProp(props, "color") == "blue" &&

               #. .. code:: de1

                                      getStrProp(props, "group") == "Encounter Powers", 1, 0)]

               #. .. code:: de1

                         [h,if(isBlue): setMacroProps(index, "color=default")]

               #. .. code:: de2

                       }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     [abort(0)] <!-- Suppress output text -->

         The way the above macro works is by getting a list of the
         macros
         `getMacros() </rptools/wiki/Macros:Functions:getMacros>`__
         which will return all the labels of the `macro
         buttons </rptools/wiki/Macro_Button>`__ on the `Current
         Token </rptools/wiki/Current_Token>`__. Since a
         `token </rptools/wiki/Token>`__ can contain multiple `macro
         buttons </rptools/wiki/Macro_Button>`__ with the same label the
         function
         `getMacroIndexes() </rptools/wiki/Macros:Functions:getMacroIndexes>`__
         is used to return the unique index of each `macro
         button </rptools/wiki/Macro_Button>`__ for each of the labels.
         Then we use
         `getMacroProps() </rptools/wiki/Macros:Functions:getMacroProps>`__
         to get the properties of the `macro
         button </rptools/wiki/Macro_Button>`__ in a `string property
         list </rptools/wiki/Macros:string_property_list>`__. The color
         of the `macro button </rptools/wiki/Macro_Button>`__ is
         extracted from this using
         `getStrProp() </rptools/wiki/Macros:Functions:getStrProp>`__
         and we check to see if it is "blue", if it is we also check to
         see if it is in the "Encounter Powers" group, and set the value
         of isBlue based on this. Then if isBlue is true (non zero) we
         use
         `setMacroProps() </rptools/wiki/Macros:Functions:setMacroProps>`__
         to change the color back to the default.

         You can test this macro by dragging a
         `token </rptools/wiki/Token>`__ onto the map and adding a
         `macro button </rptools/wiki/Macro_Button>`__ to it called
         "Something or other" in the "Encounter Powers" group and set it
         to blue in the creation dialog.

         |ButtonSomethingOrOtherBlueGroup.png|
         |ButtonSomethingOrOtherDefaultGroup.png|

         .. rubric:: Extended Rest, resetting color of buttons starting
            with "Encounter Powers" or "Daily Powers"
            :name: extended-rest-resetting-color-of-buttons-starting-with-encounter-powers-or-daily-powers

         For an extended rest we want to reset the color of any `macro
         buttons </rptools/wiki/Macro_Button>`__ that start with either
         "Encounter Powers" or "Daily Powers". So create a `campaign
         macro </rptools/wiki/Introduction_to_Macro_Writing#Campaign_Macros>`__
         called "Extended Rest" (don't forget to check the `Apply to
         Selected
         Tokens </maptool/index.php?title=Macros:Apply_to_Selected_Tokens&action=edit&redlink=1>`__
         check box) and copy the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

               #. .. code:: de1

                      

               #. .. code:: de1

                     [h,foreach(macro, getMacros()), code: {

               #. .. code:: de1

                       <!-- 

               #. .. code:: de2

                         == each label can appear more than once (i.e. more than one

               #. .. code:: de1

                         == button with same label, so we need to get all the button

               #. .. code:: de1

                         == indexes for a label

               #. .. code:: de1

                       -->

               #. .. code:: de1

                      

               #. .. code:: de2

                       [h,foreach(index, getMacroIndexes(macro)), code: {

               #. .. code:: de1

                         [props = getMacroProps(index)]

               #. .. code:: de1

                         [isBlue = if(getStrProp(props, "color") == "blue" &&

               #. .. code:: de1

                                        matches(getStrProp(props, "group"),

               #. .. code:: de1

                                               "(Daily|Encounter) Powers"), 1, 0)]

               #. .. code:: de2

                         [h,if(isBlue): setMacroProps(index, "color=default")]

               #. .. code:: de1

                       }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     [abort(0)] <!-- Suppress output text -->

         The only difference between this macro and the previous one is
         where it checks the group of the `macro
         button </rptools/wiki/Macro_Button>`__. In the "Short Rest"
         `macro button </rptools/wiki/Macro_Button>`__ we had

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               12. .. code:: de1

                          [isBlue = if(getStrProp(props, "color") == "blue" &&

               13. .. code:: de1

                                       getStrProp(props, "group") == "Encounter Powers", 1, 0)]

         Where as in the "Extended Rest" `macro
         button </rptools/wiki/Macro_Button>`__ it is

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               12. .. code:: de1

                          [isBlue = if(getStrProp(props, "color") == "blue" &&

               13. .. code:: de1

                                         matches(getStrProp(props, "group"),

               14. .. code:: de1

                                                "(Daily|Encounter) Powers"), 1, 0)]

         The pattern *(Daily|Encounter) Powers* matches both the "Daily
         Powers" and "Encounter Powers" strings. Hopefully from this you
         can see how to add powers with different durations, say you
         wanted to add powers that could be used once per round and
         place them in the "Round Group", for your "New Round" macro
         which resets the color you would change the lines to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               12. .. code:: de1

                          [isBlue = if(getStrProp(props, "color") == "blue" &&

               13. .. code:: de1

                                       getStrProp(props, "group") == "Round Powers", 1, 0)]

         And for your "Short Rest" you would change it to refresh
         encounter and round powers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               12. .. code:: de1

                          [isBlue = if(getStrProp(props, "color") == "blue" &&

               13. .. code:: de1

                                         matches(getStrProp(props, "group"),

               14. .. code:: de1

                                                "(Round|Encounter) Powers"), 1, 0)]

         And for your "Extended Rest" you would change it to refresh
         daily, encounter and round powers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               12. .. code:: de1

                          [isBlue = if(getStrProp(props, "color") == "blue" &&

               13. .. code:: de1

                                         matches(getStrProp(props, "group"),

               14. .. code:: de1

                                                "(Round|Encounter|Daily) Powers"), 1, 0)]

         .. rubric:: Using Powers, or getting the blues...
            :name: using-powers-or-getting-the-blues...

         So now all that is left is to set the color of the buttons when
         they are used. As of 1.3b48 there is no way to determine which
         button has been pressed from a macro, but what you can do is to
         add code like the following to your power macros.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                         [h: setMacroProps("Burning Hands", "color=blue")]

         Replacing the "Burning Hands" with the label of your `macro
         button </rptools/wiki/Macro_Button>`__. So lets try it, on your
         token create a `macro button </rptools/wiki/Macro_Button>`__
         called "Sleep" in the group called "Daily Powers" and in the
         button place the following code

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     Watch, the watch, you are getting sleepy, your eyelids are getting heavy.... [h: setMacroProps("Sleep", "color=blue")]

         Click on the button and hopefully you should see it change to
         blue.

         .. rubric:: Multiple Power Buttons with the same name
            :name: multiple-power-buttons-with-the-same-name

         A word of warning though the above method will change the color
         of all buttons with that label so if you have duplicates and
         only want to set one (you may want to implement multi use per
         day powers as multiple buttons for example)

         Drag a new `token </rptools/wiki/Token>`__ onto the map and
         change its name to Lib:DnD4ePowers, and create a `macro
         button </rptools/wiki/Macro_Button>`__ called "UseDailyPower",
         then copy in the following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: found = 0]

               #. .. code:: de1

                     [h: indexes = getMacroIndexes(macro.args)]

               #. .. code:: de1

                     [h, foreach(button, indexes), code: {

               #. .. code:: de1

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code:: de1

                             [group = getStrProp(props, "group")]

               #. .. code:: de1

                             [color = getStrProp(props, "color")]

               #. .. code:: de1

                             [if(color=="default" && group == "Daily Powers"): 

               #. .. code:: de1

                                 setMacroProps(button, "color=blue")

               #. .. code:: de2

                             ]

               #. .. code:: de1

                             [if(color=="default" && group == "Daily Powers"): found=1]

               #. .. code:: de1

                         }]

               #. .. code:: de1

                     }]

         This will loop through all of the indexes for the `macro
         buttons </rptools/wiki/Macro_Button>`__ with the specified name
         searching for one that is the default color and a daily power,
         once it finds one it sets its color to blue and sets found=1 so
         no other buttons are changed (as of 1.3b48 there is no way to
         break out of a loop).

         Now create a `macro button </rptools/wiki/Macro_Button>`__
         called "Lay On Hands" and copy the following in.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                         Oooh tingly!

               #. .. code:: de1

                         [h,macro("UseDailyPower@Lib:DnD4ePowers"): "Lay On Hands"]

         Duplicate that a few times and then when you click on on of the
         buttons then one of the "Lay On Hands" buttons will turn blue.

         Fine you say but I would like to stop players using powers that
         are blue (or in the case of multi use powers where there are no
         non blue ones remaining).

         We can do that by changing the "UseDailyPower" macro we created
         above on the Lib:DnD4ePowers `library
         token </rptools/wiki/Token:library_token>`__. Change it to the
         following

         .. rubric:: Sorry Sir/Madam, you have already used that!
            :name: sorry-sirmadam-you-have-already-used-that

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: found = 0]

               #. .. code:: de1

                     [h: indexes = getMacroIndexes(macro.args)]

               #. .. code:: de1

                     [h, foreach(button, indexes), code: {

               #. .. code:: de1

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code:: de1

                             [group = getStrProp(props, "group")]

               #. .. code:: de1

                             [color = getStrProp(props, "color")]

               #. .. code:: de1

                             [if(color=="default" && group == "Daily Powers"): 

               #. .. code:: de1

                                 setMacroProps(button, "color=blue")

               #. .. code:: de2

                             ]

               #. .. code:: de1

                             [if(color=="default" && group == "Daily Powers"): found=1]

               #. .. code:: de1

                         }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     <!-- if "free" one is not found then inform user they can't do it -->

               #. .. code:: de2

                     [if(found==0), code: {

               #. .. code:: de1

                         [dialog("PowerUsed"):  {

               #. .. code:: de1

                             <title>Can Not Use Power</title>

               #. .. code:: de1

                             <meta name="temporary" content="true">

               #. .. code:: de1

                             You have already used [r: macro.args]

               #. .. code:: de2

                         }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     [abort(found)] <!-- Abort the macro if an unused power was not found -->

         And change the `token </rptools/wiki/Token>`__'s "Lay On Hands"
         macro code (don't forget to change all the duplicates too).

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                         [h,macro("UsePower@Lib:DnD4ePowers"): "Daily:Lay On Hands"]

               #. .. code:: de1

                         Oooh tingly!

         Then clickity, clickity, click on the "Daily:Lay On Hands"
         buttons and when you have none left you should get the
         following dialog.

         |PowerUsedDialogGroup.png|

         It ain't pretty but the concept is there and you can easily
         expand on it to pretty it up.

         While we are at it we should add a "UseEncounterPower" macro to
         Lib:DnD4ePowers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: found = 0]

               #. .. code:: de1

                     [h: indexes = getMacroIndexes(macro.args)]

               #. .. code:: de1

                     [h, foreach(button, indexes), code: {

               #. .. code:: de1

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code:: de1

                             [group = getStrProp(props, "group")]

               #. .. code:: de1

                             [color = getStrProp(props, "color")]

               #. .. code:: de1

                             [if(color=="default" && group == "Encounter Powers"): 

               #. .. code:: de1

                                 setMacroProps(button, "color=blue")

               #. .. code:: de2

                             ]

               #. .. code:: de1

                             [if(color=="default" && group == "Encounter Powers"): found=1]

               #. .. code:: de1

                         }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     <!-- if "free" one is not found then inform user they can't do it -->

               #. .. code:: de2

                     [if(found==0), code: {

               #. .. code:: de1

                         [dialog("PowerUsed"):  {

               #. .. code:: de1

                             <title>Can Not Use Power</title>

               #. .. code:: de1

                             <meta name="temporary" content="true">

               #. .. code:: de1

                             You have already used [r: macro.args]

               #. .. code:: de2

                         }]

               #. .. code:: de1

                     }]

               #. .. code:: de1

                     [abort(found)] <!-- Abort the macro if an unused power was not found -->

         You can also use this for cases where there is only a single
         button for a power.

         You can download this part of the tutorial in in a `campaign
         file <http://lmwcs.com/maptool/campaigns/ButtonChange2.cmpgn>`__
         which was made using MapTool 1.3b48.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&oldid=5601"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Tutorial </rptools/wiki/Category:Tutorial>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Tutorial </rptools/wiki/Category:Tutorial>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Updating+Macro+Buttons+Using+a+Macro+%28Group+Method%29>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
            -  `Discussion </maptool/index.php?title=Talk:Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
            -  `View
               source </maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&action=edit>`__
            -  `View
               history </maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&oldid=5601>`__
            -  `Page
               information </maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Group_Method)&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 19 July 2011, at 16:06.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |ShortRest1MacroButton.png| image:: /maptool/images/9/97/ShortRest1MacroButton.png
   :width: 866px
   :height: 377px
   :target: /rptools/wiki/File:ShortRest1MacroButton.png
.. |ButtonSomethingOrOtherBlueGroup.png| image:: /maptool/images/9/90/ButtonSomethingOrOtherBlueGroup.png
   :width: 392px
   :height: 218px
   :target: /rptools/wiki/File:ButtonSomethingOrOtherBlueGroup.png
.. |ButtonSomethingOrOtherDefaultGroup.png| image:: /maptool/images/9/9d/ButtonSomethingOrOtherDefaultGroup.png
   :width: 392px
   :height: 218px
   :target: /rptools/wiki/File:ButtonSomethingOrOtherDefaultGroup.png
.. |PowerUsedDialogGroup.png| image:: /maptool/images/8/83/PowerUsedDialogGroup.png
   :width: 401px
   :height: 202px
   :target: /rptools/wiki/File:PowerUsedDialogGroup.png
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
