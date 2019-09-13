## Updating color of our macro buttons using DnD4e as an example

For an example I will use DnD4e powers, when a power is used it will
then update the button to show this. Although this is example is for
DnD4e the technique is applicable for many other systems.

Lets assume that you have a macro groups named "Daily Powers" and
"Encounter Powers" where we place all of our powers, and we want to set
the color of the [macro button](Macro_Button "wikilink") to blue if the
power has been used. If you want another way to do this without using
different groups see [Tracking Used DnD 4e Powers (Macro Prefix
Method)](Tutorials:Macros:UpdatingMacroButtons:DnD4ePowersPrefix "wikilink")

**Version update:** This tutorial was written before 1.3b50. As of
1.3b50 you can use
[getMacroButtonIndex](Macros:Functions:getMacroButtonIndex "wikilink")
to determine the index of the button that was pressed instead of
setting/getting the properties of the button by name you can use the
index of the button in place of the name, this way you will not run the
risk of updating buttons with the same name.

### Short Rest, resetting color of buttons in the "Encounter Powers" group

So first we will create a [macro button](Macro_Button "wikilink") called
"Short Rest", for this tutorial I will assume you just create it as a
[campaign
macro](Introduction_to_Macro_Writing#Campaign_Macros "wikilink") --just
remember to check the [Apply to Selected
Tokens](Macros:Apply_to_Selected_Tokens "wikilink") check mark-- you can
just as easily create these as macros in [library
token](Token:library_token "wikilink") macros and call them from from
[macro buttons](Macro_Button "wikilink") on your
[tokens](Token "wikilink").

[image:ShortRest1MacroButton.png](image:ShortRest1MacroButton.png "wikilink")

So create the "Short Rest" [macro button](Macro_Button "wikilink") and
copy the following code into it.

``` mtmacro numberLines
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
                 getStrProp(props, "group") == "Encounter Powers", 1, 0)]
    [h,if(isBlue): setMacroProps(index, "color=default")]
  }]
}]
[abort(0)] <!-- Suppress output text -->
```

The way the above macro works is by getting a list of the macros
[getMacros()](Macros:Functions:getMacros "wikilink") which will return
all the labels of the [macro buttons](Macro_Button "wikilink") on the
[Current Token](Current_Token "wikilink"). Since a
[token](Token "wikilink") can contain multiple [macro
buttons](Macro_Button "wikilink") with the same label the function
[getMacroIndexes()](Macros:Functions:getMacroIndexes "wikilink") is used
to return the unique index of each [macro
button](Macro_Button "wikilink") for each of the labels. Then we use
[getMacroProps()](Macros:Functions:getMacroProps "wikilink") to get the
properties of the [macro button](Macro_Button "wikilink") in a [string
property list](Macros:string_property_list "wikilink"). The color of the
[macro button](Macro_Button "wikilink") is extracted from this using
[getStrProp()](Macros:Functions:getStrProp "wikilink") and we check to
see if it is "blue", if it is we also check to see if it is in the
"Encounter Powers" group, and set the value of isBlue based on this.
Then if isBlue is true (non zero) we use
[setMacroProps()](Macros:Functions:setMacroProps "wikilink") to change
the color back to the default.

You can test this macro by dragging a [token](Token "wikilink") onto the
map and adding a [macro button](Macro_Button "wikilink") to it called
"Something or other" in the "Encounter Powers" group and set it to blue
in the creation dialog.

[image:ButtonSomethingOrOtherBlueGroup.png](image:ButtonSomethingOrOtherBlueGroup.png "wikilink")
[image:ButtonSomethingOrOtherDefaultGroup.png](image:ButtonSomethingOrOtherDefaultGroup.png "wikilink")

### Extended Rest, resetting color of buttons starting with "Encounter Powers" or "Daily Powers"

For an extended rest we want to reset the color of any [macro
buttons](Macro_Button "wikilink") that start with either "Encounter
Powers" or "Daily Powers". So create a [campaign
macro](Introduction_to_Macro_Writing#Campaign_Macros "wikilink") called
"Extended Rest" (don't forget to check the [Apply to Selected
Tokens](Macros:Apply_to_Selected_Tokens "wikilink") check box) and copy
the following code into it.

``` mtmacro numberLines
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
                   matches(getStrProp(props, "group"),
                          "(Daily|Encounter) Powers"), 1, 0)]
    [h,if(isBlue): setMacroProps(index, "color=default")]
  }]
}]
[abort(0)] <!-- Suppress output text -->
```

The only difference between this macro and the previous one is where it
checks the group of the [macro button](Macro_Button "wikilink"). In the
"Short Rest" [macro button](Macro_Button "wikilink") we had

``` mtmacro numberLines
    [isBlue = if(getStrProp(props, "color") == "blue" &&
                 getStrProp(props, "group") == "Encounter Powers", 1, 0)]
```

Where as in the "Extended Rest" [macro button](Macro_Button "wikilink")
it is

``` mtmacro numberLines
    [isBlue = if(getStrProp(props, "color") == "blue" &&
                   matches(getStrProp(props, "group"),
                          "(Daily|Encounter) Powers"), 1, 0)]
```

The pattern *(Daily|Encounter) Powers* matches both the "Daily Powers"
and "Encounter Powers" strings. Hopefully from this you can see how to
add powers with different durations, say you wanted to add powers that
could be used once per round and place them in the "Round Group", for
your "New Round" macro which resets the color you would change the lines
to

``` mtmacro numberLines
    [isBlue = if(getStrProp(props, "color") == "blue" &&
                 getStrProp(props, "group") == "Round Powers", 1, 0)]
```

And for your "Short Rest" you would change it to refresh encounter and
round powers.

``` mtmacro numberLines
    [isBlue = if(getStrProp(props, "color") == "blue" &&
                   matches(getStrProp(props, "group"),
                          "(Round|Encounter) Powers"), 1, 0)]
```

And for your "Extended Rest" you would change it to refresh daily,
encounter and round powers.

``` mtmacro numberLines
    [isBlue = if(getStrProp(props, "color") == "blue" &&
                   matches(getStrProp(props, "group"),
                          "(Round|Encounter|Daily) Powers"), 1, 0)]
```

### Using Powers, or getting the blues...

So now all that is left is to set the color of the buttons when they are
used. As of 1.3b48 there is no way to determine which button has been
pressed from a macro, but what you can do is to add code like the
following to your power macros.

``` mtmacro numberLines
    [h: setMacroProps("Burning Hands", "color=blue")]
```

Replacing the "Burning Hands" with the label of your [macro
button](Macro_Button "wikilink"). So lets try it, on your token create a
[macro button](Macro_Button "wikilink") called "Sleep" in the group
called "Daily Powers" and in the button place the following code

``` mtmacro numberLines
Watch, the watch, you are getting sleepy, your eyelids are getting heavy.... [h: setMacroProps("Sleep", "color=blue")]
```

Click on the button and hopefully you should see it change to blue.

### Multiple Power Buttons with the same name

A word of warning though the above method will change the color of all
buttons with that label so if you have duplicates and only want to set
one (you may want to implement multi use per day powers as multiple
buttons for example)

Drag a new [token](Token "wikilink") onto the map and change its name to
Lib:DnD4ePowers, and create a [macro button](Macro_Button "wikilink")
called "UseDailyPower", then copy in the following code.

``` mtmacro numberLines
[h: found = 0]
[h: indexes = getMacroIndexes(macro.args)]
[h, foreach(button, indexes), code: {
    [if(found==0), code: {
        [props = getMacroProps(button)]
        [group = getStrProp(props, "group")]
        [color = getStrProp(props, "color")]
        [if(color=="default" && group == "Daily Powers"):
            setMacroProps(button, "color=blue")
        ]
        [if(color=="default" && group == "Daily Powers"): found=1]
    }]
}]
```

This will loop through all of the indexes for the [macro
buttons](Macro_Button "wikilink") with the specified name searching for
one that is the default color and a daily power, once it finds one it
sets its color to blue and sets found=1 so no other buttons are changed
(as of 1.3b48 there is no way to break out of a loop).

Now create a [macro button](Macro_Button "wikilink") called "Lay On
Hands" and copy the following in.

``` mtmacro numberLines
    Oooh tingly!
    [h,macro("UseDailyPower@Lib:DnD4ePowers"): "Lay On Hands"]
```

Duplicate that a few times and then when you click on on of the buttons
then one of the "Lay On Hands" buttons will turn blue.

Fine you say but I would like to stop players using powers that are blue
(or in the case of multi use powers where there are no non blue ones
remaining).

We can do that by changing the "UseDailyPower" macro we created above on
the Lib:DnD4ePowers [library token](Token:library_token "wikilink").
Change it to the following

### Sorry Sir/Madam, you have already used that\!

``` mtmacro numberLines
[h: found = 0]
[h: indexes = getMacroIndexes(macro.args)]
[h, foreach(button, indexes), code: {
    [if(found==0), code: {
        [props = getMacroProps(button)]
        [group = getStrProp(props, "group")]
        [color = getStrProp(props, "color")]
        [if(color=="default" && group == "Daily Powers"):
            setMacroProps(button, "color=blue")
        ]
        [if(color=="default" && group == "Daily Powers"): found=1]
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
```

And change the [token](Token "wikilink")'s "Lay On Hands" macro code
(don't forget to change all the duplicates too).

``` mtmacro numberLines
    [h,macro("UsePower@Lib:DnD4ePowers"): "Daily:Lay On Hands"]
    Oooh tingly!
```

Then clickity, clickity, click on the "Daily:Lay On Hands" buttons and
when you have none left you should get the following dialog.

[image:PowerUsedDialogGroup.png](image:PowerUsedDialogGroup.png "wikilink")

It ain't pretty but the concept is there and you can easily expand on it
to pretty it up.

While we are at it we should add a "UseEncounterPower" macro to
Lib:DnD4ePowers.

``` mtmacro numberLines
[h: found = 0]
[h: indexes = getMacroIndexes(macro.args)]
[h, foreach(button, indexes), code: {
    [if(found==0), code: {
        [props = getMacroProps(button)]
        [group = getStrProp(props, "group")]
        [color = getStrProp(props, "color")]
        [if(color=="default" && group == "Encounter Powers"):
            setMacroProps(button, "color=blue")
        ]
        [if(color=="default" && group == "Encounter Powers"): found=1]
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
```

You can also use this for cases where there is only a single button for
a power.

You can download this part of the tutorial in in a [campaign
file](http://lmwcs.com/maptool/campaigns/ButtonChange2.cmpgn) which was
made using MapTool 1.3b48.

[Category:Tutorial](Category:Tutorial "wikilink")