================================================================
Updating Macro Buttons Using a Macro (Label Method) - MapToolDoc
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

   .. rubric:: Updating Macro Buttons Using a Macro (Label Method)
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

            -  `1 Updating the Label of our macro buttons using DnD4e as
               an
               Example. <#Updating_the_Label_of_our_macro_buttons_using_DnD4e_as_an_Example.>`__

               -  `1.1 Short Rest, resetting label of buttons in the
                  "Encounter Powers"
                  group <#Short_Rest.2C_resetting_label_of_buttons_in_the_.22Encounter_Powers.22_group>`__
               -  `1.2 Extended Rest, resetting label of buttons in the
                  "Encounter Powers" and "Daily
                  Powers"group <#Extended_Rest.2C_resetting_label_of_buttons_in_the_.22Encounter_Powers.22_and_.22Daily_Powers.22group>`__
               -  `1.3 Marking Powers as
                  Used <#Marking_Powers_as_Used>`__
               -  `1.4 Multiple Power Buttons with the same
                  name <#Multiple_Power_Buttons_with_the_same_name>`__

         .. rubric:: Updating the Label of our macro buttons using DnD4e
            as an Example.
            :name: updating-the-label-of-our-macro-buttons-using-dnd4e-as-an-example.

         For an example I will use DnD4e powers, when a power is used it
         will then update the button to show this. Although this is
         example is for DnD4e the technique is applicable for many other
         systems.

         Lets assume that you have a macro groups named "Daily Powers"
         and "Encounter Powers" where we place all of our powers, and we
         want to set the color of the macro button to blue if the power
         has been used. If you want another way to do this without using
         different groups see Tracking Used DnD 4e Powers (Macro Prefix
         Method)

         | 
         | **Version update:** This tutorial was written before 1.3b50.
           As of 1.3b50 you can use
           `getMacroButtonIndex <Macros:Functions:getMacroButtonIndex>`__
           to determine the index of the button that was pressed instead
           of setting/getting the properties of the button by name you
           can use the index of the button in place of the name, this
           way you will not run the risk of updating buttons with the
           same name.

         | 

         .. rubric:: Short Rest, resetting label of buttons in the
            "Encounter Powers" group
            :name: short-rest-resetting-label-of-buttons-in-the-encounter-powers-group

         So first we create a `macro
         button <Macro_Button>`__ called "Short Rest", for
         this tutorial I will assume that you create it as a `campaign
         macro <Introduction_to_Macro_Writing#Campaign_Macros>`__
         --just remember to check the `Apply to Selected
         Tokens </maptool/index.php?title=Macros:Apply_to_Selected_Tokens&action=edit&redlink=1>`__
         check mark-- you can just as easily create these as macros in
         `library token <Token:library_token>`__ macros
         and call them from from `macro
         buttons <Macro_Button>`__ on your
         `tokens <Token>`__.

         |ShortRest1MacroButton.png|

         So create the "Short Rest" `macro
         button <Macro_Button>`__ and copy the following
         code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [foreach(macro,getMacros()), code: {

               #. .. code-block:: none

                       <!-- 

               #. .. code:: de2

                         == each label can appear more than once (i.e. more than one

               #. .. code-block:: none

                         == button with same label, so we need to get all the button

               #. .. code-block:: none

                         == indexes for a label

               #. .. code-block:: none

                       -->

               #. .. code-block:: none

                      

               #. .. code:: de2

                         [foreach(index, getMacroIndexes(macro)), code: {

               #. .. code-block:: none

                             [h:props = getMacroProps(index)]

               #. .. code-block:: none

                             [label = getStrProp(props, "label")]

               #. .. code-block:: none

                             [isUsed = matches(label, ".* \\(Used\\)")]

               #. .. code-block:: none

                             [isEnc = matches(getStrProp(props, "group"), "Encounter Powers")]

               #. .. code:: de2

                             [if(isUsed && isEnc): setMacroProps(index, "label="+

               #. .. code-block:: none

                                 replace(label, " \\(Used\\)", ""))]

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     [abort(0)] <!-- Suppress the macros output -->

         This macro will get the labels of all the macros with
         `getMacros() <Macros:Functions:getMacros>`__. It
         will then loop through all of these labels and get the index
         for each `macro button <Macro_Button>`__ with
         that label. Then it will check to see if the macro label ends
         with the text "(Used)" if it does and it is in the "Encounter
         Powers" group it will use the
         `replace() <Macros:Functions:replace>`__ function
         to replace the " (Used)" with nothing ("") there by removing it
         from the label.

         You can test this by creating a macro on your
         `token <Token>`__ called "Something or other
         (Used)" with a group of "Encounter Powers", impersonating the
         token and clicking on the "Short Rest" `macro
         button <Macro_Button>`__.

         | 
         | |ButtonSomethingOrOtherUsed.png|
           |ButtonSomethingOrOtherNotUsed.png|

         .. rubric:: Extended Rest, resetting label of buttons in the
            "Encounter Powers" and "Daily Powers"group
            :name: extended-rest-resetting-label-of-buttons-in-the-encounter-powers-and-daily-powersgroup

         For an extended rest we want to reset the color of any `macro
         buttons <Macro_Button>`__ that start with either
         "Encounter:" or "Daily:". So create a `campaign
         macro <Introduction_to_Macro_Writing#Campaign_Macros>`__
         called "Extended Rest" (don't forget to check the `Apply to
         Selected
         Tokens </maptool/index.php?title=Macros:Apply_to_Selected_Tokens&action=edit&redlink=1>`__
         check box) and copy the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [foreach(macro,getMacros()), code: {

               #. .. code-block:: none

                       <!-- 

               #. .. code:: de2

                         == each label can appear more than once (i.e. more than one

               #. .. code-block:: none

                         == button with same label, so we need to get all the button

               #. .. code-block:: none

                         == indexes for a label

               #. .. code-block:: none

                       -->

               #. .. code-block:: none

                      

               #. .. code:: de2

                         [foreach(index, getMacroIndexes(macro)), code: {

               #. .. code-block:: none

                             [h:props = getMacroProps(index)]

               #. .. code-block:: none

                             [label = getStrProp(props, "label")]

               #. .. code-block:: none

                             [isUsed = matches(label, ".* \\(Used\\)")]

               #. .. code-block:: none

                             [isEnc = matches(getStrProp(props, "group"), "(Encounter|Daily) Powers")]

               #. .. code:: de2

                             [if(isUsed && isEnc): setMacroProps(index, "label="+

               #. .. code-block:: none

                                 replace(label, " \\(Used\\)", ""))]

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     [abort(0)] <!-- Suppress the macros output -->

         The only difference between this macro and the previous one is
         where it checks the group. For "Short Rest" it is.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               14. .. code-block:: none

                              [isEnc = matches(getStrProp(props, "group"), "Encounter Powers")]

         Where as for "Extended Rest" it is.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               14. .. code-block:: none

                              [isEnc = matches(getStrProp(props, "group"), "(Encounter|Daily) Powers")]

         The pattern (Daily|Encounter) Powers matches both the "Daily
         Powers" and "Encounter Powers" strings. Hopefully from this you
         can see how to add powers with different durations, say you
         wanted to add powers that could be used once per round and
         place them in the "Round Group", for your "New Round" macro
         which resets the label you would change the lines to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               14. .. code-block:: none

                              [isEnc = matches(getStrProp(props, "group"), "Round Powers")]

         And for your "Short Rest" you would change it to refresh
         encounter and round powers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               14. .. code-block:: none

                              [isEnc = matches(getStrProp(props, "group"), "(Round|Encounter) Powers")]

         And for your "Extended Rest" you would change it to refresh
         daily, encounter and round powers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               14. .. code-block:: none

                              [isEnc = matches(getStrProp(props, "group"), "(Round|Encounter|Daily) Powers")]

         .. rubric:: Marking Powers as Used
            :name: marking-powers-as-used

         So now all that is left is to set the color of the buttons when
         they are used. As of 1.3b48 there is no way to determine which
         button has been pressed from a macro, but what you can do is to
         add code like the following to your power macros.

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                         [h: setMacroProps("Burning Hands", "Burning Hands (Used)"]

         Replacing both occurrences of "Burning Hands" with the label of
         your `macro button <Macro_Button>`__. So lets try
         it, on your `token <Token>`__ create a `macro
         button <Macro_Button>`__ called "Sleep " in the
         group called "Daily Powers" and in the button place the
         following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                           Watch, the watch, you are getting sleepy, your eyelids are getting heavy.... [h: setMacroProps("Sleep", "label=Sleep (Used)")]

         Click on the button and hopefully you should see it change.

         .. rubric:: Multiple Power Buttons with the same name
            :name: multiple-power-buttons-with-the-same-name

         A word of warning though the above method will change the color
         of all buttons with that label so if you have duplicates and
         only want to set one (you may want to implement multi use per
         day powers as multiple buttons for example)

         Drag a new `token <Token>`__ onto the map and
         change its name to Lib:DnD4ePowers, and create a `macro
         button <Macro_Button>`__ called "UseDailyPower",
         then copy in the following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [found = 0]

               #. .. code-block:: none

                     [indexes = getMacroIndexes(macro.args)]

               #. .. code-block:: none

                     [foreach(button, indexes), code: {

               #. .. code-block:: none

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code-block:: none

                             [label = getStrProp(props, "label")]

               #. .. code-block:: none

                             [isPower = matches(label, macro.args)]

               #. .. code-block:: none

                             [isDay = matches(getStrProp(props, "group"), 

               #. .. code-block:: none

                                                    "Daily Powers")]

               #. .. code:: de2

                             [if(isPower == 1 && isDay == 1 && found == 0): 

               #. .. code-block:: none

                                 setMacroProps(button, "label=" + label + " (Used)")

               #. .. code-block:: none

                             ]

               #. .. code-block:: none

                             [if(isPower == 1 && isDay == 1 && found == 0): found=1]

               #. .. code-block:: none

                         }]

               #. .. code:: de2

                     }]

         This will loop through all of the indexes for the `macro
         buttons <Macro_Button>`__ with the specified name
         and if it finds one and it is in the "Daily Powers" group it
         will append " (Used)" to it. If you have more than one button
         it will append " (Used)" to each one as you push one of the
         buttons.

         Now create a `macro button <Macro_Button>`__
         called "Lay On Hands" and copy the following in.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                         Oooh tingly!

               #. .. code-block:: none

                         [h, macro("UseDailyPower@Lib:DnD4ePowers"): "Lay On Hands"]

         Duplicate that a few times and then when you click on on of the
         buttons then one of the "Lay On Hands" buttons will change to
         "Lay On Hands (Used)".

         Fine you say but I would like to stop players using powers that
         are used (or in the case of multi use powers where there are no
         non used ones remaining).

         We can do that by changing the "UseDailyPower" macro we created
         above on the Lib:DnD4ePowers `library
         token <Token:library_token>`__. Change it to the
         following

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [found = 0]

               #. .. code-block:: none

                     [indexes = getMacroIndexes(macro.args)]

               #. .. code-block:: none

                     [foreach(button, indexes), code: {

               #. .. code-block:: none

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code-block:: none

                             [label = getStrProp(props, "label")]

               #. .. code-block:: none

                             [isPower = matches(label, macro.args)]

               #. .. code-block:: none

                             [isDay = matches(getStrProp(props, "group"), 

               #. .. code-block:: none

                                                    "Daily Powers")]

               #. .. code:: de2

                             [if(isPower == 1 && isDay == 1 && found == 0): 

               #. .. code-block:: none

                                 setMacroProps(button, "label=" + label + " (Used)")

               #. .. code-block:: none

                             ]

               #. .. code-block:: none

                             [if(isPower == 1 && isDay == 1 && found == 0): found=1]

               #. .. code-block:: none

                         }]

               #. .. code:: de2

                     }]

               #. .. code-block:: none

                     <!-- if "free" one is not found then inform user they can't do it -->

               #. .. code-block:: none

                     [if(found==0), code: {

               #. .. code-block:: none

                         [dialog("PowerUsed"):  {

               #. .. code-block:: none

                             <title>Can Not Use Power</title>

               #. .. code:: de2

                             <meta name="temporary" content="true">

               #. .. code-block:: none

                             You have already used [r: macro.args]

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     [abort(found)] <!-- Abort the macro if an unused power was not found -->

         |PowerUsedDialogGroup.png|

         It ain't pretty but the concept is there and you can easily
         expand on it to pretty it up.

         While we are at it we should add a "UseEncounterPower" macro to
         Lib:DnD4ePowers.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [found = 0]

               #. .. code-block:: none

                     [indexes = getMacroIndexes(macro.args)]

               #. .. code-block:: none

                     [foreach(button, indexes), code: {

               #. .. code-block:: none

                         [if(found==0), code: {

               #. .. code:: de2

                             [props = getMacroProps(button)]

               #. .. code-block:: none

                             [label = getStrProp(props, "label")]

               #. .. code-block:: none

                             [isPower = matches(label, macro.args)]

               #. .. code-block:: none

                             [isEnc = matches(getStrProp(props, "group"), 

               #. .. code-block:: none

                                                    "Daily Powers")]

               #. .. code:: de2

                             [if(isPower == 1 && isEnc == 1 && found == 0): 

               #. .. code-block:: none

                                 setMacroProps(button, "label=" + label + " (Used)")

               #. .. code-block:: none

                             ]

               #. .. code-block:: none

                             [if(isPower == 1 && isEnc == 1 && found == 0): found=1]

               #. .. code-block:: none

                         }]

               #. .. code:: de2

                     }]

               #. .. code-block:: none

                     <!-- if "free" one is not found then inform user they can't do it -->

               #. .. code-block:: none

                     [if(found==0), code: {

               #. .. code-block:: none

                         [dialog("PowerUsed"):  {

               #. .. code-block:: none

                             <title>Can Not Use Power</title>

               #. .. code:: de2

                             <meta name="temporary" content="true">

               #. .. code-block:: none

                             You have already used [r: macro.args]

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     [abort(found)] <!-- Abort the macro if an unused power was not found -->

         You can also use this for cases where there is only a single
         button for a power.

         You can download this part of the tutorial in in a `campaign
         file <http://lmwcs.com/maptool/campaigns/ButtonChange3.cmpgn>`__
         which was made using MapTool 1.3b48.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Updating_Macro_Buttons_Using_a_Macro_(Label_Method)&oldid=5605"

