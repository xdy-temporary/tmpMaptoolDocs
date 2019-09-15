.. contents::
   :depth: 3
..

.. _updating_color_of_our_macro_buttons_using_dnd4e_as_an_example:

Updating color of our macro buttons using DnD4e as an example
=============================================================

For an example I will use DnD4e powers, when a power is used it will
then update the button to show this. Although this is example is for
DnD4e the technique is applicable for many other systems.

For the first set up lets assume that we have prefixed our powers with
"Daily:" for daily powers and "Encounter:" for encounter powers, and we
want to set the color of the `macro button <Macro_Button>`__ to blue if
the power has been used. If you want another way to do this without
having to place "Daily:" or "Encounter:" in front of your power see
`Tracking Used DnD 4e Powers (Macro Group
Method) <Tutorials:Macros:UpdatingMacroButtons:DnD4ePowersGroup>`__

**Version update:** This tutorial was written before 1.3b50. As of
1.3b50 you can use
`getMacroButtonIndex <Macros:Functions:getMacroButtonIndex>`__ to
determine the index of the button that was pressed instead of
setting/getting the properties of the button by name you can use the
index of the button in place of the name, this way you will not run the
risk of updating buttons with the same name.

.. _short_rest_resetting_color_of_buttons_starting_with_encounter:

Short Rest, resetting color of buttons starting with "Encounter:"
-----------------------------------------------------------------

So first we will create a `macro button <Macro_Button>`__ called "Short
Rest", for this tutorial I will assume you just create it as a `campaign
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

   [h,foreach(macro, getMacros()), code: {
     <!-- 
       == each label can appear more than once (i.e. more than one
       == button with same label, so we need to get all the button
       == indexes for a label
     -->

     [h,foreach(index, getMacroIndexes(macro)), code: {
       [props = getMacroProps(index)]
       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "Encounter:.*"),  1, 0)]
       [h,if(isBlue): setMacroProps(index, "color=default")]
     }]
   }]
   [abort(0)] <!-- Suppress output text -->

The way the above macro works is by getting a list of the macros
`getMacros() <Macros:Functions:getMacros>`__ which will return all the
labels of the `macro buttons <Macro_Button>`__ on the `Current
Token <Current_Token>`__. Since a `token <Token>`__ can contain multiple
`macro buttons <Macro_Button>`__ with the same label the function
`getMacroIndexes() <Macros:Functions:getMacroIndexes>`__ is used to
return the unique index of each `macro button <Macro_Button>`__ for each
of the labels. Then we use
`getMacroProps() <Macros:Functions:getMacroProps>`__ to get the
properties of the `macro button <Macro_Button>`__ in a `string property
list <Macros:string_property_list>`__. The color of the `macro
button <Macro_Button>`__ is extracted from this using
`getStrProp() <Macros:Functions:getStrProp>`__ and we check to see if it
is "blue", if it is we also check to see if the label of the button
starts with "Encounter:" and set the value of isBlue based on this. Then
if isBlue is true (non zero) we use
`setMacroProps() <Macros:Functions:setMacroProps>`__ to change the color
back to the default.

You can test this macro by dragging a `token <Token>`__ onto the map and
adding a `macro button <Macro_Button>`__ to it called
"Encounter:Something or other" and set it to blue in the creation
dialog.

`image:ButtonSomethingOrOtherBlue.png <image:ButtonSomethingOrOtherBlue.png>`__
`image:ButtonSomethingOrOtherDefault.png <image:ButtonSomethingOrOtherDefault.png>`__

.. _extended_rest_resetting_color_of_buttons_starting_with_encounter_or_daily:

Extended Rest, resetting color of buttons starting with "Encounter:" or "Daily:"
--------------------------------------------------------------------------------

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

   [h,foreach(macro, getMacros()), code: {
     <!-- 
       == each label can appear more than once (i.e. more than one
       == button with same label, so we need to get all the button
       == indexes for a label
     -->

     [h,foreach(index, getMacroIndexes(macro)), code: {
       [props = getMacroProps(index)]
       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "(Daily|Encounter):.*"),  1, 0)]
       [h,if(isBlue): setMacroProps(index, "color=default")]
     }]
   }]
   [abort(0)] <!-- Suppress output text -->

The only difference between this macro and the previous one is where it
checks the prefix of the `macro button <Macro_Button>`__. In the "Short
Rest" `macro button <Macro_Button>`__ we had

.. code:: mtmacro
   :number-lines: 12

       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "Encounter:.*"),  1, 0)]

Where as in the "Extended Rest" `macro button <Macro_Button>`__ it is

.. code:: mtmacro
   :number-lines: 12

       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "(Daily|Encounter):.*"),  1, 0)]

The pattern *(Daily|Encounter):.\** matches a string that starts with
either "Daily:" or "Encounter:". Hopefully from this you can see how to
add powers with different durations, say you wanted to add powers that
could be used once per round and you prefix them with "Round:", for your
"New Round" macro which resets the color you would change the lines to

.. code:: mtmacro
   :number-lines: 12

       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "Round:.*"),  1, 0)]

And for your "Short Rest" you would change it to refresh encounter and
round powers.

.. code:: mtmacro
   :number-lines: 12

       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "(Round|Encounter):.*"),  1, 0)]

And for your "Extended Rest" you would change it to refresh daily,
encounter and round powers.

.. code:: mtmacro
   :number-lines: 12

       [isBlue = if(getStrProp(props, "color") == "blue" &&
                      matches(macro, "(Round|Encounter|Daily):.*"),  1, 0)]

.. _using_powers_or_getting_the_blues...:

Using Powers, or getting the blues...
-------------------------------------

So now all that is left is to set the color of the buttons when they are
used. As of 1.3b48 there is no way to determine which button has been
pressed from a macro, but what you can do is to add code like the
following to your power macros.

.. code:: mtmacro
   :number-lines:

       [h: setMacroProps("Encouner:Burning Hands", "color=blue")]

Replacing the "Encounter:Burning Hands" with the label of your `macro
button <Macro_Button>`__. So lets try it, on your token create a `macro
button <Macro_Button>`__ called "Daily:Sleep" and in the button place
the following code

.. code:: mtmacro
   :number-lines:

   Watch, the watch, you are getting sleepy, your eyelids are getting heavy.... [h: setMacroProps("Daily:Sleep", "color=blue")]

Click on the button and hopefully you should see it changE to blue.

.. _multiple_power_buttons_with_the_same_name:

Multiple Power Buttons with the same name
-----------------------------------------

A word of warning though the above method will change the color of all
buttons with that label so if you have duplicates and only want to set
one (you may want to implement multi use per day powers as multiple
buttons for example)

Drag a new `token <Token:token>`__ onto the map and change its name to
Lib:DnD4ePowers, and create a `macro button <Macro_Button>`__ called
"UsePower", then copy in the following code.

.. code:: mtmacro
   :number-lines:

   [h: found = 0]
   [h: indexes = getMacroIndexes(macro.args)]
   [h, foreach(button, indexes), code: {
       [if(found==0), code: {
           [color = getStrProp(getMacroProps(button), "color")]
           [if(color=="default"): setMacroProps(button, "color=blue")]
           [if(color=="default"): found=1]
       }]
   }]

This will loop through all of the indexes for the `macro
buttons <Macro_Button>`__ with the specified name searching for one that
is the default color, once it finds one it sets its color to blue and
sets found=1 so no other buttons are changed (as of 1.3b48 there is no
way to break out of a loop).

Now create a `macro button <Macro_Button>`__ called "Daily:Lay On Hands"
and copy the following in.

.. code:: mtmacro
   :number-lines:

       Oooh tingly!
       [h,macro("UsePower@Lib:DnD4ePowers"): "Daily:Lay On Hands"]

Duplicate that a few times and then when you click on on of the buttons
then one of the "Daily:Lay On Hands" buttons will turn blue.

Fine you say but I would like to stop players using powers that are blue
(or in the case of multi use powers where there are no non blue ones
remaining).

We can do that by changing the "UsePower" macro we created above on the
Lib:DnD4ePowers `library token <Token:library_token>`__. Change it to
the following

.. _sorry_sirmadam_you_have_already_used_that:

Sorry Sir/Madam, you have already used that!
--------------------------------------------

.. code:: mtmacro
   :number-lines:

   [h: found = 0]
   [h: indexes = getMacroIndexes(macro.args)]
   [h, foreach(button, indexes), code: {
       [if(found==0), code: {
           [color = getStrProp(getMacroProps(button), "color")]
           [if(color=="default"): setMacroProps(button, "color=blue")]
           [if(color=="default"): found=1]
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

And change the `Token:token <Token:token>`__'s "Daily:Lay On Hands"
macro code (don't forget to change all the duplicates too).

.. code:: mtmacro
   :number-lines:

       [h,macro("UsePower@Lib:DnD4ePowers"): "Daily:Lay On Hands"]
       Oooh tingly!

Then clickity, clickity, click on the "Daily:Lay On Hands" buttons and
when you have none left you should get the following dialog.

`image:PowerUsedDialog.png <image:PowerUsedDialog.png>`__

It ain't pretty but the concept is there and you can easily expand on it
to pretty it up.

You can also use this for cases where there is only a single button for
a power.

You can download this part of the tutorial in in a `campaign
file <http://lmwcs.com/maptool/campaigns/ButtonChange1.cmpgn>`__ which
was made using MapTool 1.3b48.

`Category:Tutorial <Category:Tutorial>`__
