.. contents::
   :depth: 3
..

.. _updating_the_label_of_our_macro_buttons_using_dnd4e_as_an_example.:

Updating the Label of our macro buttons using DnD4e as an Example.
==================================================================

For an example I will use DnD4e powers, when a power is used it will
then update the button to show this. Although this is example is for
DnD4e the technique is applicable for many other systems.

Lets assume that you have a macro groups named "Daily Powers" and
"Encounter Powers" where we place all of our powers, and we want to set
the color of the macro button to blue if the power has been used. If you
want another way to do this without using different groups see Tracking
Used DnD 4e Powers (Macro Prefix Method)

**Version update:** This tutorial was written before 1.3b50. As of
1.3b50 you can use
`getMacroButtonIndex <Macros:Functions:getMacroButtonIndex>`__ to
determine the index of the button that was pressed instead of
setting/getting the properties of the button by name you can use the
index of the button in place of the name, this way you will not run the
risk of updating buttons with the same name.

.. _short_rest_resetting_label_of_buttons_in_the_encounter_powers_group:

Short Rest, resetting label of buttons in the "Encounter Powers" group
----------------------------------------------------------------------

So first we create a `macro button <Macro_Button>`__ called "Short
Rest", for this tutorial I will assume that you create it as a `campaign
macro <Introduction_to_Macro_Writing#Campaign_Macros>`__ --just remember
to check the `Apply to Selected
Tokens <Macros:Apply_to_Selected_Tokens>`__ check mark-- you can just as
easily create these as macros in `library token <Token:library_token>`__
macros and call them from from `macro buttons <Macro_Button>`__ on your
`tokens <Token>`__.

`image:ShortRest1MacroButton.png <image:ShortRest1MacroButton.png>`__

So create the "Short Rest" `macro button <Macro_Button>`__ and copy the
following code into it.

.. code:: mtmacro
   :number-lines:

   [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

   [foreach(macro,getMacros()), code: {
     <!-- 
       == each label can appear more than once (i.e. more than one
       == button with same label, so we need to get all the button
       == indexes for a label
     -->

       [foreach(index, getMacroIndexes(macro)), code: {
           [h:props = getMacroProps(index)]
           [label = getStrProp(props, "label")]
           [isUsed = matches(label, ".* \\(Used\\)")]
           [isEnc = matches(getStrProp(props, "group"), "Encounter Powers")]
           [if(isUsed && isEnc): setMacroProps(index, "label="+
               replace(label, " \\(Used\\)", ""))]
       }]
   }]
   [abort(0)] <!-- Suppress the macros output -->

This macro will get the labels of all the macros with
`getMacros() <Macros:Functions:getMacros>`__. It will then loop through
all of these labels and get the index for each `macro
button <Macro_Button>`__ with that label. Then it will check to see if
the macro label ends with the text "(Used)" if it does and it is in the
"Encounter Powers" group it will use the
`replace() <Macros:Functions:replace>`__ function to replace the "
(Used)" with nothing ("") there by removing it from the label.

You can test this by creating a macro on your `token <Token>`__ called
"Something or other (Used)" with a group of "Encounter Powers",
impersonating the token and clicking on the "Short Rest" `macro
button <Macro_Button>`__.

`image:ButtonSomethingOrOtherUsed.png <image:ButtonSomethingOrOtherUsed.png>`__
`image:ButtonSomethingOrOtherNotUsed.png <image:ButtonSomethingOrOtherNotUsed.png>`__

.. _extended_rest_resetting_label_of_buttons_in_the_encounter_powers_and_daily_powersgroup:

Extended Rest, resetting label of buttons in the "Encounter Powers" and "Daily Powers"group
-------------------------------------------------------------------------------------------

For an extended rest we want to reset the color of any `macro
buttons <Macro_Button>`__ that start with either "Encounter:" or
"Daily:". So create a `campaign
macro <Introduction_to_Macro_Writing#Campaign_Macros>`__ called
"Extended Rest" (don't forget to check the `Apply to Selected
Tokens <Macros:Apply_to_Selected_Tokens>`__ check box) and copy the
following code into it.

.. code:: mtmacro
   :number-lines:

   [abort(hasImpersonated())] <!-- Abort macro if no token is impersonated -->

   [foreach(macro,getMacros()), code: {
     <!-- 
       == each label can appear more than once (i.e. more than one
       == button with same label, so we need to get all the button
       == indexes for a label
     -->

       [foreach(index, getMacroIndexes(macro)), code: {
           [h:props = getMacroProps(index)]
           [label = getStrProp(props, "label")]
           [isUsed = matches(label, ".* \\(Used\\)")]
           [isEnc = matches(getStrProp(props, "group"), "(Encounter|Daily) Powers")]
           [if(isUsed && isEnc): setMacroProps(index, "label="+
               replace(label, " \\(Used\\)", ""))]
       }]
   }]
   [abort(0)] <!-- Suppress the macros output -->

The only difference between this macro and the previous one is where it
checks the group. For "Short Rest" it is.

.. code:: mtmacro
   :number-lines: 14

           [isEnc = matches(getStrProp(props, "group"), "Encounter Powers")]

Where as for "Extended Rest" it is.

.. code:: mtmacro
   :number-lines: 14

           [isEnc = matches(getStrProp(props, "group"), "(Encounter|Daily) Powers")]

The pattern (Daily|Encounter) Powers matches both the "Daily Powers" and
"Encounter Powers" strings. Hopefully from this you can see how to add
powers with different durations, say you wanted to add powers that could
be used once per round and place them in the "Round Group", for your
"New Round" macro which resets the label you would change the lines to

.. code:: mtmacro
   :number-lines: 14

           [isEnc = matches(getStrProp(props, "group"), "Round Powers")]

And for your "Short Rest" you would change it to refresh encounter and
round powers.

.. code:: mtmacro
   :number-lines: 14

           [isEnc = matches(getStrProp(props, "group"), "(Round|Encounter) Powers")]

And for your "Extended Rest" you would change it to refresh daily,
encounter and round powers.

.. code:: mtmacro
   :number-lines: 14

           [isEnc = matches(getStrProp(props, "group"), "(Round|Encounter|Daily) Powers")]

.. _marking_powers_as_used:

Marking Powers as Used
----------------------

So now all that is left is to set the color of the buttons when they are
used. As of 1.3b48 there is no way to determine which button has been
pressed from a macro, but what you can do is to add code like the
following to your power macros.

.. code:: mtmacro
   :number-lines:

       [h: setMacroProps("Burning Hands", "Burning Hands (Used)"]

Replacing both occurrences of "Burning Hands" with the label of your
`macro button <Macro_Button>`__. So lets try it, on your
`token <Token>`__ create a `macro button <Macro_Button>`__ called "Sleep
" in the group called "Daily Powers" and in the button place the
following code.

.. code:: mtmacro
   :number-lines:

         Watch, the watch, you are getting sleepy, your eyelids are getting heavy.... [h: setMacroProps("Sleep", "label=Sleep (Used)")] 

Click on the button and hopefully you should see it change.

.. _multiple_power_buttons_with_the_same_name:

Multiple Power Buttons with the same name
-----------------------------------------

A word of warning though the above method will change the color of all
buttons with that label so if you have duplicates and only want to set
one (you may want to implement multi use per day powers as multiple
buttons for example)

Drag a new `token <Token>`__ onto the map and change its name to
Lib:DnD4ePowers, and create a `macro button <Macro_Button>`__ called
"UseDailyPower", then copy in the following code.

.. code:: mtmacro
   :number-lines:

   [found = 0]
   [indexes = getMacroIndexes(macro.args)]
   [foreach(button, indexes), code: {
       [if(found==0), code: {
           [props = getMacroProps(button)]
           [label = getStrProp(props, "label")]
           [isPower = matches(label, macro.args)]
           [isDay = matches(getStrProp(props, "group"), 
                                  "Daily Powers")]
           [if(isPower == 1 && isDay == 1 && found == 0): 
               setMacroProps(button, "label=" + label + " (Used)")
           ]
           [if(isPower == 1 && isDay == 1 && found == 0): found=1]
       }]
   }]

This will loop through all of the indexes for the `macro
buttons <Macro_Button>`__ with the specified name and if it finds one
and it is in the "Daily Powers" group it will append " (Used)" to it. If
you have more than one button it will append " (Used)" to each one as
you push one of the buttons.

Now create a `macro button <Macro_Button>`__ called "Lay On Hands" and
copy the following in.

.. code:: mtmacro
   :number-lines:

       Oooh tingly!
       [h, macro("UseDailyPower@Lib:DnD4ePowers"): "Lay On Hands"]

Duplicate that a few times and then when you click on on of the buttons
then one of the "Lay On Hands" buttons will change to "Lay On Hands
(Used)".

Fine you say but I would like to stop players using powers that are used
(or in the case of multi use powers where there are no non used ones
remaining).

We can do that by changing the "UseDailyPower" macro we created above on
the Lib:DnD4ePowers `library token <Token:library_token>`__. Change it
to the following

.. code:: mtmacro
   :number-lines:

   [found = 0]
   [indexes = getMacroIndexes(macro.args)]
   [foreach(button, indexes), code: {
       [if(found==0), code: {
           [props = getMacroProps(button)]
           [label = getStrProp(props, "label")]
           [isPower = matches(label, macro.args)]
           [isDay = matches(getStrProp(props, "group"), 
                                  "Daily Powers")]
           [if(isPower == 1 && isDay == 1 && found == 0): 
               setMacroProps(button, "label=" + label + " (Used)")
           ]
           [if(isPower == 1 && isDay == 1 && found == 0): found=1]
       }]
   }]
   <!-- if "free" one is not found then inform user they can't do it -->
   [if(found==0), code: {
       [dialog("PowerUsed"):  {
           <title>Can Not Use Power</title>
           <meta name="temporary" content="true">
           You have already used [r: macro.args]
       }]
   }]
   [abort(found)] <!-- Abort the macro if an unused power was not found -->

`image:PowerUsedDialogGroup.png <image:PowerUsedDialogGroup.png>`__

It ain't pretty but the concept is there and you can easily expand on it
to pretty it up.

While we are at it we should add a "UseEncounterPower" macro to
Lib:DnD4ePowers.

.. code:: mtmacro
   :number-lines:

   [found = 0]
   [indexes = getMacroIndexes(macro.args)]
   [foreach(button, indexes), code: {
       [if(found==0), code: {
           [props = getMacroProps(button)]
           [label = getStrProp(props, "label")]
           [isPower = matches(label, macro.args)]
           [isEnc = matches(getStrProp(props, "group"), 
                                  "Daily Powers")]
           [if(isPower == 1 && isEnc == 1 && found == 0): 
               setMacroProps(button, "label=" + label + " (Used)")
           ]
           [if(isPower == 1 && isEnc == 1 && found == 0): found=1]
       }]
   }]
   <!-- if "free" one is not found then inform user they can't do it -->
   [if(found==0), code: {
       [dialog("PowerUsed"):  {
           <title>Can Not Use Power</title>
           <meta name="temporary" content="true">
           You have already used [r: macro.args]
       }]
   }]
   [abort(found)] <!-- Abort the macro if an unused power was not found -->

You can also use this for cases where there is only a single button for
a power.

You can download this part of the tutorial in in a `campaign
file <http://lmwcs.com/maptool/campaigns/ButtonChange3.cmpgn>`__ which
was made using MapTool 1.3b48.

`Category:Tutorial <Category:Tutorial>`__
