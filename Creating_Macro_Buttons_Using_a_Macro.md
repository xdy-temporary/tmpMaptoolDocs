## Introduction

The following tutorial illustrates one method of creating macro buttons
for a token based on user input. In this particular case, the macros
illustrated below are used to configure a new token with several buttons
illustrating different powers that the character represented by the
token possesses. The tutorial is directly applicable to the *Dungeons &
Dragons 4th Edition* game system, but the concepts in it may be
applicable to other game systems. This tutorial may also be useful in
conjunction with the tutorials on changing macro buttons.

### Assumptions

The button creation macro illustrated below is actually one component of
a much larger sequence of macros, so in order to understand what is
happening, there are a few assumptions to be made.

1\. Powers in this campaign setup are stored in a series of [token
properties](Token:token_property "wikilink") with the names "Power0",
"Power1", "Power2", and so on. These token properties contain power
information in the form of a [string property
list](Macros:string_property_list "wikilink") with the format:

``` mtmacro numberLines
powername=Melee Basic Attack ; action=standard ; usage=at-will ; attack=5 ;
against=AC ; targets=one creature ; damage=1d6+5 ; critdamage=11 ; damtype= ;
hitEffect=--none-- ; missEffect=--none-- ; atktype=melee ;
range=weapon ; expended=Available ; reliable=0 ; special=--none-- ;
```

2\. This macro will receive from a calling macro an argument called
[*macro.args*](Macros:Special_Variables:macro.args "wikilink") that
contains a number (which will be used to determine which power - Power0,
Power1, etc. - will have a new button created).

3\. This macro in particular is the final step in a macro sequence, so
it is assumed that when this macro is called, the string property list
for the power in question has already been populated.

## Macro Code and Explanation

The [full macro
code](Tutorials:Macros:create_buttons_full_code "wikilink") is broken
down and explained below.

### Receiving Arguments and Assigning Variables

``` mtmacro numberLines
[h:powerSlot=macro.args]
[h:pname=getStrProp(eval("Power"+powerSlot),"powername")]
[h:use=getStrProp(eval("Power"+powerSlot),"usage")]
```

This section of the macro simply assigns the value of *macro.args* to a
new variable, *powerSlot*. The variable *powerSlot* is then used in line
2 to extract the name of the power (the *powername* key in the string
property) and assign it to *pname*, and to extract the *usage* value
from the string property as well.

### Requesting User Input

``` mtmacro numberLines
[h:status=input(
    "addButtons|Yes,No|Add Macro Buttons to your token?|RADIO|ORIENT=H SELECT=1"
)]
[h:abort(status)]
```

This section is a simple [input()](Macros:Functions:input "wikilink")
function that confirms whether the user wants to add the button to their
token's macro set. This is important because if a macro button is
already present, this macro will create a duplicate. Frequently,
however, users will want to simply update their power information,
rather than create a new button.

### Checking for the Power's Use Limits and Setting Colors

``` mtmacro numberLines
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
```

This is probably the most complex piece of the macro: a
[SWITCH()](Macros:Branching_and_Looping#SWITCH_Option "wikilink") roll
option nested inside an
[IF()](Macros:Branching_and_Looping#IF_Option "wikilink") option, both
of which use the [CODE:{
}](Macros:Branching_and_Looping#CODE "wikilink") option to execute
multiple macro commands as a single block.

However, functionally, this segment's purpose is to assign several
variables (to be used later) based on whether the power is an at-will,
encounter, daily, or rechargeable power; remember that this entire
SWITCH() block is contained within the first code block of the IF()
statement.

### Building the Macro Button Contents

``` mtmacro numberLines
[h:macroProps="autoexec=true;"]
[h:macroProps=setStrProp(macroProps,"color",bcolor)]
[h:macroProps=setStrProp(macroProps,"fontColor",fcolor)]
[h:macroProps=setStrProp(macroProps,"group",group)]
[h:grayoutString=""]
[h,IF(grayout): grayoutString=encode("[h:setMacroProps(" + "'" +pname+ "'" + ",'color=gray;' " + ")]")]
[h:command=encode("[h:thisPower="+"'"+pname+"'"+"]")]
[h:command=command+encode("[h:index=getMacroIndexes(thisPower)]")]
[h:command=command+encode("[h:mProps=getMacroProps(index)]")]
[h:command=command+encode("[h:color=getStrProp(mProps,'color')]")]
[h:command=command+encode("[h:used=if(color=='gray', 0, 1)]")]
[h:command=command+encode("[h:abort(used)]")]
[h:command=command + encode("[MACRO('AttackMain@Lib:test'):thisPower]")]
[h:command=command+grayoutString]
```

This sequence may appear confusing, but it is conceptually relatively
simple. Because a macro button must contain macro instructions, this
segment of macro code builds a string using the
[encode()](Macros:Functions:encode "wikilink") function.

In this case, **encode()** is used because macro commands require the
square bracket (\[ \]), but the macro parser has a tendency to attempt
to evaluate anything in square brackets as a command, which - if you get
a quotation mark out of place - will cause various frustrating and
eldritch errors. To prevent this, we use single and double quotation
marks to ensure that each element of the final string is treated as a
string, and then **encode()** the whole result to a single string.

Specifically:

  - Lines 1-4 set the macro properties based on the output of the
    earlier **SWITCH()** statement, each step adding an additional
    key-value pair to the macro property string.
  - Lines 5-6 check to see if the *grayout* variable is true, and if so
    create an encoded string adding a command to change the color of the
    button to gray when the button is clicked.
  - Lines 7-1 iteratively assemble the *command* variable as an encoded
    string (the steps are broken down to make sure that the strings are
    handled properly by the parser). These steps create a sequence of
    commands that will, when the user clicks the button:

<!-- end list -->

1.  Call a macro on a [library token](Token:library_token "wikilink") to
    resolve the use of the power
2.  If the macro is an encounter or daily power, change the macro button
    color to gray
3.  If the macro is an encounter or daily power, prevent the macro from
    executing if the button is clicked again

### Creating the Macro Button

``` mtmacro numberLines
[h:createMacro(pname, decode(command), macroProps)]
Buttons added.
};
```

This step is the easy part\! We call the
[createMacro()](Macros:Functions:createMacro "wikilink") function and
pass the arguments *pname* (containing the power's name), the
[decoded](Macros:Functions:decode "wikilink") *command* string
(containing all of the macro commands we wish the new button to
contain), and the variable *macroProps* (which sets the initial button
and font colors, group, and other properties we wish the new button to
have).

Note that line three contains the closing brace of this CODE() block -
be sure to close your CODE blocks properly\!

### Mop-Up

``` mtmacro numberLines
{
No buttons added to token.
};]
```

This tiny section at the very end is what is executed if the user does
*not* wish to add buttons to their token. It is the *false_body* of the
IF(), and will simply echo "No buttons added to token." to the chat
window.

## The Result

When this macro is finished processing, the end result is that the token
in question should have a new macro button generated containing the
command sequence we assembled in the *command* variable. An example of
the output - using the sample string property list shown in the
[Assumptions](Tutorials:Macros:CreatingMacroButtons#Assumptions "wikilink")
section - is shown below:

``` mtmacro numberLines
[h:thisPower='Melee Basic Attack']
[MACRO('AttackMain@Lib:test'):thisPower]
```

Another sample, this one including the *grayout* power information as
well as the additional code to prevent repeat execution of the macro:

``` mtmacro numberLines
[h:thisPower='Chain Lightning']
[h:index=getMacroIndexes(thisPower)]
[h:mProps=getMacroProps(index)]
[h:color=getStrProp(mProps,'color')]
[h:used=if(color=='gray', 0, 1)]
[h:abort(used)]
[MACRO('AttackMain@Lib:test'):thisPower]
[h:setMacroProps('Chain Lightning','color=gray;' )]
```

**NOTE**: Although I have introduced line breaks in the examples above
for ease of reading, the actual commands in the macro button do not have
any line breaks between them. It requires some relatively convoluted use
of strings and string concatenation to create easy-to-read command
sequences via . Future builds of MapTool should remedy this situation.

## See Also

, ,

[Category:Tutorial](Category:Tutorial "wikilink")