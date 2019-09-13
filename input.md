inputType{{\!}}options"}} }} '''Sub-Parameters      and separated by a
space.}}

### Input Types and Options

#### TEXT

Creates a text box containing the  or . The contents typed in the box
are assigned to the variable, and there is no limit to the length of the
data that can be entered.

##### TEXT Options

nnn|Sets the width of the text box; defaults to 16}}.}} TRUE|Causes the
to be hidden and allows the  to span the width of the dialog; defaults
to FALSE}}. If hidden the  text is used as a tooltip.}}

-----

#### LIST

Creates a drop-down list of choices. The variable is assigned the index
(starting at ) of the item that was selected. The  sub-parameter is a
comma delimited list of the values that can be chosen.

##### LIST Options

nnn|Sets the index of the initial selection in the drop-down list (the
first item is number ); defaults to 0}}.}} STRING|The variable is
assigned the string contents of the selected item instead of the index;
defaults to NUMBER}}.}} TRUE|If the string for the item contains a space
and then an image asset URL, the image is displayed in the entry;
defaults to FALSE}}. Text before the URL is used for the entry's text.
The  and  functions can be used to obtain asset URLs.}} nnn|The size the
icons; defaults to 50}}. All icons are stretched to fit a square this
size. If the asset URL points to an image that is not square, some
distortion will occur.}} FALSE|No text is shown in the list entries next
to the icons; defaults to TRUE}}, and is ignored if no icon is set.}}
TRUE|Causes the  to be hidden and allows the  to span the width of the
dialog; defaults to FALSE}}. If hidden the  text is used as a tooltip.}}

-----

#### CHECK

Creates a checkbox. The variable is assigned either  (unchecked) or
(checked).

##### CHECK Options

TRUE|Causes the  to be hidden and allows the  to span the width of the
dialog; defaults to FALSE}}. If hidden the  text is used as a tooltip.}}

-----

#### RADIO

Creates a group of radio buttons. This option works much like ,
returning the index of the choice that was selected.

##### RADIO Options

H|Arranges the radio buttons horizontally on a single line; defaults to
V}}.}} nnn|Sets the initially selected radio button (the first item is
number ); defaults to 0}}.}} STRING|The variable is assigned the string
contents of the selected item instead of the index; defaults to
NUMBER}}.}} TRUE|Causes the  to be hidden and allows the  to span the
width of the dialog; defaults to FALSE}}. If hidden the  text is used as
title placed in the border of the radio button group.}}

-----

#### LABEL

Creates a static label. The  is ignored, and nothing is assigned to it.

##### LABEL Options

TRUE|If the string for the  contains a space and then an image asset
URL, the image is displayed; defaults to FALSE}}.}} nnn|The size the
icon; defaults to 50}}. The icon is stretched to fit a square this size.
If the asset URL points to an image that is not square, some distortion
will occur.}} FALSE|The  is not shown; defaults to TRUE}}.}} TRUE|Causes
the  to be hidden and allows the  to span the width of the dialog;
defaults to FALSE}}. If hidden the  text is used as a tooltip.}}

-----

#### PROPS

Creates a bordered sub-area containing multiple text boxes, one for each
entry in a [String Property List](String_Property_List "wikilink")
stored in . The  is assigned a new string property containing all the
entries with their updated values.

##### PROPS Options

SUFFIXED|Makes a variable assignment for each of the sub-values, with an
underscore appended to the name; defaults to NONE}}.}} UNSUFFIXED|Makes
variable assignments to unmodified variable names.  is usually
preferred, unless you are not using variable names that match [Token
Properties](Token_Property "wikilink") or if you specifically intend to
overwrite them.}} TRUE|Causes the  to be hidden and allows the  to span
the width of the dialog; defaults to FALSE}}. If hidden the  text is
used as title placed in the border of the  group.}}

-----

#### TAB

Creates a tab for a tabbed dialog box. The  variable gets assigned a
[String Property List](String_Property_List "wikilink") containing all
the variable assignments made on this tab. Since some of the variables
may be property strings themselves, the tab property string uses the
non-default delimiter . When using tabs, the first  must be a .

##### TAB Options

TRUE|Causes this tab to be displayed when the dialog appears; defaults
to FALSE}}.}}

-----

**TAB Example**

``` mtmacro numberLines
[H: input(
     "tab0 | Info || TAB",
     "Name ## Rank ## Serial number | 1,2,3 || LIST",
     "tab1 | Abilities || TAB",
     "Strength ## Dexterity ## Wisdom"
)]
```

|examples=

**1. A simple input() requesting 3 different text variables.**

``` mtmacro numberLines
[input("AtkBonus", "DmgBonus", "CombatAdvantage")]
```

Displays:

![Image:simple-input.jpg](simple-input.jpg "Image:simple-input.jpg")

Note that only the  is required to generate an input dialog - if that is
all that is provided,  assumes that each  will be assigned using a text
field.

**2. A more complex input, including LABEL, CHECK, and TEXT fields.**

``` mtmacro numberLines
[h:status=input(
    "junkVar|"+powerClicked+"|Selected Power|LABEL",
    "ComAdv|0|Combat Advantage|CHECK",
    "MarkPenalty|0|Marked by an enemy other than your target|CHECK",
    "TargetConcealed|0|Target has Concealment|CHECK",
    "MiscBonus|0|Miscellaneous BONUSES to your attack roll",
    "MiscPenalty|0|Miscellaneous PENALTIES to your attack roll",
    "mdb|0|Miscellaneous BONUS to Damage")]
[h:abort(status)]
```

Displays:

![Image:Input-checksntext.jpg](Input-checksntext.jpg
"Image:Input-checksntext.jpg")

Recall that , as the  for a  control, has no value assigned to it. In
this example, we assume  is a variable that is passed in some fashion to
the macro generating this input. It is incorporated using the standard
method of concatenating a variable into a string (). Finally, observe
that the variable  is assigned the value returned by the  function, and
the  function is called using the value of . In this fashion, the macro
is terminated if the user clicks the ***Cancel*** button or hits the
***ESC*** key.

**3. An input showing several LIST boxes, as well as the VALUE=STRING
option.**

``` mtmacro numberLines
[h:status=input(
    "targetNum|"+imgList+"|Select Target|LIST|SELECT=0 ICON=TRUE ICONSIZE=30",
    "feature|Hunter's Quarry, Sneak Attack, Warlock's Curse|Type of Striker Damage|LIST|SELECT=0 VALUE=STRING",
    "CQSDice|1d6,1d8,2d6,2d8,3d6,3d8|Curse, Quarry, or Sneak Attack Dice|LIST|SELECT=0 VALUE=STRING",
    "critAttack|0|Was the attack a critical hit?|CHECK"
)]
```

Displays:

![Image:Input-lists.jpg](Input-lists.jpg "Image:Input-lists.jpg")

Note that the  section for each list contains a list of items, *or* a
variable containing a [String List](String_List "wikilink") (*e.g.*, the
variable ). In the first list, the  and  options are set, because that
list contains image asset URLs for token images. In the second two
lists, the STRING}} option is set so that the value in the corresponding
variable is the actual string (*e.g.* ) rather than the index of the
list item.

**4. An input using the "\#\#" delimiter trick.**

``` mtmacro numberLines
[h:inptext=""]
[h:num=1]

[h,foreach(entry,"SPD1,SPD2,SPD3,SPD4,SPD5,SPD6,SPD7,SPD8,SPD9"),code:{
  [if(num<=CMSL),code:{
    [inptext=listAppend(inptext,entry+"|"+eval(entry)+"|Level "+num,"##")]
  }]
  [num=num+1]
}]

[h:screen0=input(
  "junkvar|Include any bonus spells from high Wisdom|Enter your Cleric spells per day|LABEL",
  inptext
)]
```

In this example, variables  and  are called earlier from a token and
represent spells per day for spell levels 1-9 and the maximum spell
level accessible by the token at the moment for the class in question.
The macro is intended to allow manual changing of the number of spells
per day for the token, but the input is cleaned up and prevents
complications by not allowing for inputs to spell levels beyond what is
available. The first line in the input is a standard string, followed by
a comma. The second is a -containing string set by the  function above,
which will contain just the number of input requests, separated by 's,
needed in the situation.

**5. A much more elegant and way more sophisticated way to example no. 4
is aliasmaks(?) strformat/json.evaluate trick** If you are in need of an
 function where the number of inputs can vary like in ex. 4, you can
also opt to use a json array and use . This will look as follows:

``` mtmacro numberLines
<!-- Define local vars -->
[H: Strength = 12]
[H: Toughness = 14]
[H: Hitpoints = 20]
[H: statList = "Strength, Toughness, Hitpoints"]
[H: inputStr = "[]"]

<!-- Build input form simple -->
[H: inputStr = json.append(inputStr,"junk|<html><b>A simple example</b></html>|-|LABEL|SPAN=TRUE")]
[H: inputStr = json.append(inputStr, "Strength|"+Strength+"|Enter Strenght value")]
[H: inputStr = json.append(inputStr, "Toughness|"+Toughness+"|Enter Toughness value")]
[H: inputStr = json.append(inputStr, "Hitpoints|"+Hitpoints+"|Entere number of Hitpoints")]

<!-- Build input form advanced -->
[H: inputStr = json.append(inputStr,"junk|<html><b>A complex example</b></html>|-|LABEL|SPAN=TRUE")]
[H, foreach(stat,statList): inputStr = json.append(inputStr,strformat("%{stat}|%s|<html><b><font color=blue>Enter %{stat} value</b></font></html>|TEXT|WIDTH=6", eval(stat)))]

<!-- put local variables in input form -->
[H: inputStr = json.evaluate(inputStr)]

<!-- get user input -->
[H: hasInput = input(json.toList(inputStr,"##"))]
```

**6. An input using aliasmask's no-zero-trick** Usually, when you leave
a value blank for input it puts that annoying  in it's place. Here's one
way to avoid that. The only limitation, I suppose is that the variable
name is visible as the prompt (and the variable name/contents must be
StrProp-compatible).

*(thanks to aliasmask for the trick and biodude for stating the
limits.)*

``` mtmacro numberLines
[h:abort(input(
    "junk|<html><b>Enter player names. These should match the user names:<br><font color='red'>"+getAllPlayerNames()+"</font></html>|-|LABEL|SPAN=TRUE",
    "Enter Player Names|player0=;player1=;player2=||PROPS|SPAN=TRUE SETVARS=UNSUFFIXED"
))]
```

**7. An input using Wolph42's tooltip-trick** It is possible to use HTML
mark up by just adding HTML tags around the input text. This makes it
possible to use e.g. bold and italic tags, but also the  tag. This span
tag allows tooltips to be added anywhere via its  attribute. Here's an
example:

``` mtmacro numberLines
[H: hasInput = input(
"junk|<html>Some title text</html>|<html>here comes the tooltip text</html>|LABEL|SPAN=TRUE",
"someVariable|0|<html><span title='<html>This text will be shown as a tooltip if you hover with your mouse over the text</html>'>Do you wish to turn the <b>setting</b> on?</span></html>|CHECK"
)]
```

Another interesting trick is adding pictures to the input. This example
show the image of the selected token:

``` mtmacro numberLines
[h:input(
    "junk|<html><b>Show picture of token<br></html>|-|LABEL|SPAN=TRUE",
    "junk|<html><img src='"+getTokenImage(60)+"'></img></html>|-|LABEL|SPAN=TRUE"
)]
```

  -

    It might get fixed in **b90** but if not there is a workaround. Just
    change the last line into:

<!-- end list -->

``` mtmacro numberLines
"junk|<html><img src='"+replace(getTokenImage(), ":", ":")+"' height=60 width=60></img></html>|-|LABEL|SPAN=TRUE"
```

If you really want to go full monty on the tooltip INSIDE the input,
here's an example of what is possible (the wiki can't properly handle
all the code here so it comes out a bit funky):

``` mtmacro numberLines
[h:hasInput     = input('
    someVariable|0|<html><span title="<html>
    This setting allows for more advanced use of the movement limiter. First off: <b>In order for this to work <i>Limit Movement</i> must be<br>
    set to a number other then 0(the actual number wont be used).</b> If you enter 0 here then this setting will be ignored and the movement<br>
    will be limited to what you have set in <i>Limit Movement</i>.<br>
    <br>
    <b>Example of how to use this setting:</b><br>
    Let say that all the tokens have a characteristic: <i>Dexterity</i> and the max amount of cells a token is allowed to move is 4 x <i>Dexterity</i>.<br>
    Then what you set here is: <font bgcolor=white color=gray>[r:4*Dexterity]</font> You can enter any piece of code in here, as long as the output of that code<br>
    results in a number. The token that is moved will be the currentToken for this code! Note that if multiple tokens are moved, the first selected<br>
    token will be the currentToken.<br>
    <br>
    <b>Adding states and changing the output message</b>.<br>
    You can take this code even a step further and also change the output to the chat. This can be done by setting the predefined message variable to<br>
    something else. Here you can make use of other predefined variables as well. The default message is:<br>
    <font bgcolor=white color=gray>[h:message   = "You moved %{tok} %{usedMove} cells. The maximum allowed movement is %{limitMovement} cells."]</font><br>
    (HTML make up can be used, but is removed from this example cause it does not show in a tool-tip) Here:<br>
    <font bgcolor=white color=gray>message</font> is the actual message to the ouput. Note that strformat is used.<br>
    <font bgcolor=white color=gray>tok</font> is the name of the selected token<br>
    <font bgcolor=white color=gray>usedMove</font> is the amount of cells the token moved<br>
    <font bgcolor=white color=gray>limitMovement</font> is the max amount the token is allowed to move.<br>
    These you can use to create your own message type <b>as long as the resulting output is a number</b>. E.g.:<br>
    <font bgcolor=white color=gray>
    [r,if(getState("Dead") || getState("Incapacitated"), CODE:{
        [r:0]
        [h:message  = "%{tok} is incapacitated and cannot move"]
    };{
        [r:4*Dexterity]
    }]
    </font></html>">
    Enter code here (hover over this for more info)
    </html></span></html>
')]
```

For this to work I had to replace the quotes (") and the OR bars (||) by
there ASCII representation. This is the result:

![Image:Advanced Example Tooltip.jpg](Advanced_Example_Tooltip.jpg
"Image:Advanced Example Tooltip.jpg")

Note that this technique isn't perfect, because HTML tags inside the
may be interpreted as ending tags in the outer  block as the  function
is merely processing text and not looking at the content. }}

**8. Images in Input** It requires a bit of fiddling, but because HTML
is allowed it's possible to add images to your input functions as well
(besides the LIST trick described above). This can simply be done with
the  tags. However the preset image size, e.g. from  which retrieves the
asset ID of the token handout and presets it to a max width or height
(whichever is bigger) of 90 pixels, does work for  but not for the
rest\! Example use:

``` mtmacro numberLines
[h:input("junk|<html><img src='"+getTokenHandout(90)+"'></img></html>|-|LABEL|SPAN=TRUE")]
```

  -

    As a workaround, use this:

<!-- end list -->

``` mtmacro numberLines
[h:input("junk|<html><img src='"+replace(getTokenHandout(), ":", ":")+"' height=90 width=90></img></html>|-|LABEL|SPAN=TRUE")]
```

![Image:LABEL Picture.jpg](LABEL_Picture.jpg "Image:LABEL Picture.jpg")

For other uses, e.g. choosing a picture from a  option, you will need to
limit the image sizes using the image tags:

``` mtmacro numberLines
[h:me = getSelected()]
[h, token(me),CODE:{
    [image      = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenImage()+"'></img>   </td></tr><tr><td align='center'>Image</td> </tr></table></html>"]
    [portrait   = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenPortrait()+"'></img>    </td></tr><tr><td align='center'>Portrait</td>  </tr></table></html>"]
    [handout    = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenHandout()+"'></img> </td></tr><tr><td align='center'>Handout</td>   </tr></table></html>"]
}]

[H: abort(input(
    "junk|<html><b>Choose picture to show to players:<br></html>|-|LABEL|SPAN=TRUE",
    "picChoice|"+image+","+portrait+","+handout+"|Which picture|RADIO|ORIENT=H SELECT=2",
    "picSize|100|Size of picture (px)"
))]

[r,token(me), if(picChoice == 0): "<img src='"+getTokenImage(picSize)+"'></img>"]
[r,token(me), if(picChoice == 1): "<img src='"+getTokenPortrait(picSize)+"'></img>"]
[r,token(me), if(picChoice == 2): "<img src='"+getTokenHandout(picSize)+"'></img>"]
```

![Image:RADIO Picture.jpg](RADIO_Picture.jpg "Image:RADIO Picture.jpg")

**9. Using PROPS**

``` mtmacro numberLines
[h: abort(input("resultVars|strength=0;toughness=0;willpower=0|Enter values|PROPS|SPAN=TRUE SETVARS=UNSUFFIXED"))]
[r:resultVars]
```

[Category:Miscellaneous
Function](Category:Miscellaneous_Function "wikilink")