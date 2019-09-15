.. contents::
   :depth: 3
..

.. _an_introduction_to_maptool_macro_dialogs_and_frames:

An Introduction to MapTool Macro Dialogs and Frames
===================================================

Please note I will be using CSS and HTML in this tutorial but I will not
really be explaining them, if you need a refresher on either a search on
`google <http://www.google.com.au/search?q=HTML+and+CSS+Tutorials>`__
will point you to many resources that do a better job than I could.

The and `roll types <Macros:Roll:types>`__ create a new dialog or frame
where all the output from the commands within the {} will be displayed.
dialog create a dialog box that hovers over other windows. frame creates
a frame that can be docked like the other maptool windows. The dialog
and frame windows can be used to display HTML and rolls the same as the
chat output window.

This tutorial starts with the standard blank campaign you get when you
start MapTool, anything else we need we will add along the way.

.. _first_steps:

First Steps
-----------

So lets jump in and create your first dialog, you can use the code below
to create a dialog.

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
     Your first dialog!
   }]

.. figure:: FirstDialog.png
   :alt: FirstDialog.png

   FirstDialog.png

I know its pretty boring but before we start adding more to it lets
create a frame so that you can see the difference

.. code:: mtmacro
   :number-lines:

   [frame("Test"): {
     Your first frame!
   }]

.. figure:: FirstFrame.png
   :alt: FirstFrame.png

   FirstFrame.png

And a picture of your first frame docked.

.. figure:: FirstFrame-Docked.png
   :alt: FirstFrame-Docked.png

   FirstFrame-Docked.png

Back to the dialog you can spice it up a little with some `dice
rolls <Macros:Roll:types>`__ and HTML formatting.

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
     <b>1d4</b> -> [1d4]<br>
     <b>1d6</b> -> [1d6]<br>
     <b>1d8</b> -> [1d8]<br>
     <b>1d10</b> -> [1d10]<br>
     <b>1d12</b> -> [1d12]<br>
     <b>1d20</b> -> [1d20]<br>
     <b>1d100</b> -> [1d100]<br>
   }]

.. _adding_some_html:

Adding Some HTML
----------------

This will create a dialog box with some HTML formatting and `dice
rolls <Macros:Roll:types>`__. The `dice rolls <Macros:Roll:types>`__
will have all the tooltips that you would normally get in the chat
output.

Still the title is boring (it defaults to the name of the dialog). You
can use the HTML

.. raw:: html

   <title>

tag to change the title. Run the code below, there is no need to close
the dialog from the code above.

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
     <html>
       <head>
         <title>Dice Roll Dialog</title>
       </head>
       <body>
         <b>1d4</b> -> [1d4]<br>
         <b>1d6</b> -> [1d6]<br>
         <b>1d8</b> -> [1d8]<br>
         <b>1d10</b> -> [1d10]<br>
         <b>1d12</b> -> [1d12]<br>
         <b>1d20</b> -> [1d20]<br>
         <b>1d100</b> -> [1d100]<br>
       </body>
     </html>
   }]

.. figure:: DialogTitle.png
   :alt: DialogTitle.png

   DialogTitle.png

Notice that the dialog command did not open a new dialog window, instead
it replaced the contents of the dialog you had open. When you use
[dialog()] with the name of a dialog that already exists the contents of
that dialog are replaced, (`[frame() <frame_(roll_option)>`__] works the
same way). You can use this behavior to update your dialogs. Create a
token called `Lib:Test <Library_Token>`__ with a macro (created on that
lib:Test token) called Test

Copy the following code into the Test macro.

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
     <html>
       <head>
         <title>Dice Roll Dialog</title>
       </head>
       <body>
         <b>1d4</b> -> [1d4]<br>
         <b>1d6</b> -> [1d6]<br>
         <b>1d8</b> -> [1d8]<br>
         <b>1d10</b> -> [1d10]<br>
         <b>1d12</b> -> [1d12]<br>
         <b>1d20</b> -> [1d20]<br>
         <b>1d100</b> -> [1d100]<br>
         <br>
         [macroLink("Refresh", "Test@Lib:Test")]
       </body>
     </html>
   }]

.. figure:: DialogRefresh.png
   :alt: DialogRefresh.png

   DialogRefresh.png

The above macro uses the `macroLink() <Macros:Functions:macroLink>`__
function to create a link that will call Test on
`Lib:Test <Library_Token>`__ when ever it is clicked (which will update
the dialog with new rolls).

The above would be really useful if you needed a window that provided
you with a bunch of dice rolls all the time. But I assume that is not
what most people will want to do with the dialogs.

Drag another `token <Token>`__ out on to the map, and fill in the `token
properties <Token:token_property>`__. We can create a simple character
sheet with a dialog. On the `Lib:Test <Library_Token>`__ token create a
macro called CharSheet and paste the following code into it.

.. code:: mtmacro
   :number-lines:

   [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]
   [dialog("CharSheetTest"): {
     <html>
       <head>
         <title>Character Sheet</title>
       </head>
       <body>
         <table>
           [foreach(prop, propNames, ""), code: {
             <tr>
               <td>[r: prop]</td>
               <td>[r: getProperty(prop)]</td>
             </tr>
           }]
         </table>
       </body>
     </html>
   }]

On the new `Token <Token>`__ that you placed on the map create a `macro
button <Macro_Button>`__ called CharSheet and paste the following into
it.

.. code:: mtmacro
   :number-lines:

   [macro("CharSheet@Lib:Test"): ""]
   [abort(0)]

Click on the new `macro button <Macro_Button>`__.

.. _now_for_a_dash_of_css:

Now for a dash of CSS
---------------------

Again we are not going to set the world on fire with this character
sheet dialog. Lets spice it up a little, I will show you how to use some
CSS for formatting.

To use CSS you insert a link like the following into the HTML to be
displayed.

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
       <link rel='stylesheet' type='text/css' href='myCSS@Lib:Test'></link>
   }]

Although you can (and probably should) use the
`getMacroLocation() <Macros:Functions:getMacroLocation>`__ function to
make sure it comes from the same `Lib:Token <Library_Token>`__ as the
macro. So,

.. code:: mtmacro
   :number-lines:

   [dialog("Test"): {
       <link rel='stylesheet' type='text/css' href='myCSS@[r: getMacroLocation()]'></link>
   }]

Edit the CharSheet macro on the `Lib:Test <Library_Token>`__
`Token <Token>`__ and paste in the following.

.. code:: mtmacro
   :number-lines:

   [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]
   [dialog("CharSheetTest"): {
     <html>
       <head>
         <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">
         <title>Character Sheet</title>
       </head>
       <body>
         <table id="stats">
           <tr>
             <th>Name</th>
             <th>Score</th>
           </tr>
           [h: class = "oddRow"]
           [foreach(prop, propNames, ""), code: {
             <tr class="[r:class]">
               <td>[r: prop]</td>
               <td>[r: getProperty(prop)]</td>
             </tr>
             [h: class = if(class=="oddRow", "evenRow", "oddRow")]
           }]
         </table>
       </body>
     </html>
   }]

Also create a new `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ called CharSheet_css and paste the
following CSS code into it.

.. code:: mtmacro
   :number-lines:

   .oddRow { background-color: #FFFFFF }
   .evenRow { background-color: #EEEEAA }
   #stats th { background-color: #113311; color: #FFFFFF }

Click on the CharSheet `macro button <Macro_Button>`__ on your
`Token <Token>`__.

.. figure:: CharSheetDialog2.png
   :alt: CharSheetDialog2.png

   CharSheetDialog2.png

Looks much better already!

Getting better... Lets make some more changes. Change the CharSheet
macro on `Lib:Test <Library_Token>`__ to

.. code:: mtmacro
   :number-lines:

   [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]
   [dialog("CharSheetTest"): {
     <html>
       <head>
         <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">
         <title>Character Sheet</title>
       </head>
       <body>
         <table>
           <tr>
             <td>
               <img src='[r: getTokenImage(100)]'></img>
             </td>
             <td>
               <table id="stats">
                 <tr>
                   <th>Name</th>
                   <th>Score</th>
                 </tr>
                 [h: class = "oddRow"]
                 [foreach(prop, propNames, ""), code: {
                   <tr class="[r:class]">
                     <td>[r: prop]</td>
                     <td>[r: getProperty(prop)]</td>
                   </tr>
                   [h: class = if(class=="oddRow", "evenRow", "oddRow")]
                 }]
               </table>
             </td>
           </tr>
         </table>
         <hr>
         <table>
           <tr>
             <th>Hit Points:</th>
             <td>[r: HP]</td>
             <th>Armor Class:</th>
             <td>[r: AC]</td>
           </tr>
         </table>
       </body>
     </html>
   }]

.. figure:: CharSheetDialog3.png
   :alt: CharSheetDialog3.png

   CharSheetDialog3.png

Looks much better already!

.. _and_a_touch_more_formatting:

And a Touch more formatting
---------------------------

Ok in Edit->Campaign Properties, Token Properties Tab, Basic Token type,
add the following properties

-  \*@MaxHP
-  \*@XP
-  \*@NextLevelXP

Then edit your `Token <Token>`__ and set some values in your new
`properties <Token_Property>`__.

Time to create a new `macro button <Macro_Button>`__ on the
`Lib:Test <Library_Token>`__ called TrafficLightBar and paste the
following code into it.

.. code:: mtmacro
   :number-lines:

   <!-- ======================================================================
        ====
        ==== Outputs a red/yellow/green bar
        ====
        ==== Parameters (accepts a string property list with following keys)
        ====
        ====   MaxLen - Maximum length of status bar.
        ====   MaxValue - The "Full" value for the bar.
        ====   Value - The current value for the bar.
        ====   Label - The label for the bar.
        ====
        ====================================================================== -->
   <!-- Set up the colors for our "Traffic Lights" -->
   [h: r0=200] [h: g0=200] [h: b0=200]
   [h: r1=200] [h: g1=0]   [h: b1=0]
   [h: r2=255] [h: g2=140] [h: b2=0]
   [h: r3=0]   [h: g3=200] [h: b3=0]
   [h: MaxLen=getStrProp(macro.args, "MaxLen")]
   [h: MaxValue=getStrProp(macro.args, "MaxValue")]
   [h: Value=getStrProp(macro.args, "Value")]
   [h: Label=getStrProp(macro.args, "Label")]
   [h: Len=max(min(round(Value*MaxLen/MaxValue+0.4999),MaxLen),0)]
   [h: Len=if(Value>=MaxValue,MaxLen, Len)]
   [h: c=min(round(Value*3/MaxValue+0.4999),3)]
   [h: col=min(max(Len,0),1)*c]
   [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]
   <table>
     <tr>
       <td><span title="{Value}/{MaxValue}">{Label}</span></td>
       <td style="background-color: rgb({r},{g},{b})">
         <span title="{Value}/{MaxValue}">[c(Len, ""),r: " "]</span>
       </td>
       [if(MaxLen-Len>0), code: {
         <td style="background-color: rgb({r0},{g0},{b0})">
           <span title="{Value}/{MaxValue}">[c(MaxLen-Len,""),r: " "]</span>
         </td>
       }]
     </tr>
   </table>

Create another `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ called StatusBar and copy the following
code into it.

.. code:: mtmacro
   :number-lines:

   <!-- ======================================================================
        ====
        ==== Outputs a "progress" bar
        ====
        ==== Parameters (accepts a string property list with following keys)
        ====
        ====   MaxLen - Maximum length of status bar.
        ====   MaxValue - The "Full" value for the bar.
        ====   Value - The current value for the bar.
        ====   Label - The label for the bar.
        ====   Color - R,G,B color
        ====
        ====================================================================== -->
   [h: r0=200] [h: g0=200] [h: b0=200]
   [h: MaxLen=getStrProp(macro.args, "MaxLen")]
   [h: MaxValue=getStrProp(macro.args, "MaxValue")]
   [h: Value=getStrProp(macro.args, "Value")]
   [h: Color=getStrProp(macro.args, "Color")]
   [h: Label=getStrProp(macro.args, "Label")]
   [h: r1=listGet(Color,0)]
   [h: g1=listGet(Color,1)]
   [h: b1=listGet(Color,2)]
   [h: Len=max(min(round(Value*MaxLen/MaxValue+0.4999),MaxLen),0)]
   [h: c=min(round(Value/MaxValue+0.4999),1)]
   [h: col=min(max(Len,0),1)*c]
   [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]
   [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]
   <table>
     <tr>
       <td><span title="{Value}/{MaxValue}">{Label}</span></td>
       <td style="background-color: rgb({r},{g},{b})">
         <span title="{Value}/{MaxValue}">[c(Len, ""),r: " "]</span>
       </td>
       [if(MaxLen-Len>0), code: {
         <td style="background-color: rgb({r0},{g0},{b0})">
           <span title="{Value}/{MaxValue}">[c(MaxLen-Len,""),r: " "]</span>
         </td>
       }]
     </tr>
   </table>

I am really going to gloss over the previous two functions a bit as they
are not important to understanding how to use dialogs or frames, but so
you know what they do TrafficLightBar creates a red/yellow/green bar
where the color is based on how full the bar is. StatusBar just creates
a bar that is one color.

Just a quick point for those who may not know this already, but when you
call a macro with `[macro("name"): arguments <macro_(roll_option)>`__]
the arguments are available in the macro in the variable
`macro.args <macro.args>`__. To return a value from the macro you read
the variable `macro.return <macro.return>`__, the calling macro can then
read `macro.return <macro.return>`__ to get this value.

Then we change the CharSheet macro on `Lib:Test <Library_Token>`__ to

.. code:: mtmacro
   :number-lines:

   [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]
   [dialog("CharSheetTest"): {
     <html>
       <head>
         <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">
         <title>Character Sheet</title>
       </head>
       <body>
         <table>
           <tr>
             <td>
               <img src='[r: getTokenImage(100)]'></img>
             </td>
             <td>
               <table id="stats">
                 <tr>
                   <th>Name</th>
                   <th>Score</th>
                 </tr>
                 [h: class = "oddRow"]
                 [foreach(prop, propNames, ""), code: {
                   <tr class="[r:class]">
                     <td>[r: prop]</td>
                     <td>[r: getProperty(prop)]</td>
                   </tr>
                   [h: class = if(class=="oddRow", "evenRow", "oddRow")]
                 }]
               </table>
             </td>
           </tr>
         </table>
         <hr>
         <table>
           <tr>
             <td>
               [h: hpBarArgs = strformat("MaxLen=50; Value=%{HP}; MaxValue=%{MaxHP}; Label=HP")]
               [macro("TrafficLightBar@this"): hpBarArgs]
             </td>
           </tr>
           <tr>
             <td>
               [h: hpBarArgs = strformat("MaxLen=50; Value=%{XP}; MaxValue=%{NextLevelXP}; Label=XP; Color=120,120,255")]
               [macro("StatusBar@this"): hpBarArgs]
             </td>
           </tr>
         </table>
       </body>
     </html>
   }]

Click on the CharSheet `macro button <Macro_Button>`__ on your
`Token <Token>`__ again and you will have a new character sheet.

.. figure:: CharSheetDialog4.png
   :alt: CharSheetDialog4.png

   CharSheetDialog4.png

The above example uses `strformat() <Macros:Functions:strformat>`__
which allows you to insert variables in a string using the %{*var*}
syntax. It also has other flags that can be used to format variable
output

.. _creating_support_functions:

Creating Support Functions
--------------------------

Lets leave the character sheet at this for the moment and move on to a
new example.

Edit->Campaign Properties, Token Properties Tab, Basic Token type, add
the following properties

-  Weapons
-  Items

We are going to store our weapons in a `string property
list <String_Property_List>`__ with the following keys.

-  NumWeapons - The number of weapons in our property list.
-  UsingWeapon - The weapon we are currently using.
-  WeaponXName - The name of weapon number X
-  WeaponXDamage - The damage of weapon number X
-  WeaponXBonus - The bonus of weapon number X

We could add a lot more, but lest keep it semi simple for this post.

The first thing we need is a way to enter weapons, we could use the
`input() <input>`__ function but since this is a tutorial on frames and
dialogs, I should probably show you how to do it in a dialog.

But first we need to do some set up, when the player creates a new
weapon we will need to get NumWeapons add 1 to it, save it back to the
property and use that number (lets not worry about what happens if a
player cancels the entry of the weapon as we are not really that worried
if we have gaps in our numbering scheme). One problem is though what do
we do first time around since the `string property
list <String_Property_List>`__ would be empty so trying to use the
`token property <Token_Property>`__ Weapons in strProp*() functions
would result in the user being prompted for a value. We could add a
default value in the campaign for the token, but there are also other
methods. One thing we can do is use the
`isPropertyEmpty() <isPropertyEmpty>`__ function to check if the
`property <Token_Property>`__ is empty and if so use a initial value for
it, or the `getProperty() <getProperty>`__ function that will just
return an empty string ("") not prompt if there is no
`property <Token_Property>`__.

So lets create a macro that returns the number of a new weapon. Create a
`macro button <Macro_Button>`__ called NextWeaponNumber and then paste
the following code into it.

.. code:: mtmacro
   :number-lines:

   <!--
     Returns the number for the next weapon as well as updating the
     the counter.
     -->

   <!-- If Weapons token property is empty set it to a default value -->
   [h,if(isPropertyEmpty("Weapons")): Weapons = "NumWeapons=0;"]

   [h: numWeapons = getStrProp(Weapons, "NumWeapons") + 1]

   <!-- Now update our property -->
   [h: Weapons = setStrProp(Weapons, "NumWeapons", numWeapons)]

   <!-- Finally set out return value -->
   [h: macro.return = numWeapons]

You can test it by running the following code from chat a few times

.. code:: mtmacro
   :number-lines:

   [macro("NextWeaponNumber@Lib:Test"): ""] [macro.return]

When you are done you can reset the weapon count simply by editing the
`token properties <Token_Property>`__ and clearing out the text for
weapons.

Lets also make a `macro button <Macro_Button>`__ called AddWeapon which
takes a `string property list <Macros:string_property_list>`__ with the
following keys

-  Name
-  Damage
-  Bonus
-  Number

And adds or updates the weapon in the `string property
list <Macros:string_property_list>`__.

.. code:: mtmacro
   :number-lines:

   <!--
     Adds a weapon to the Weapons property list

     Parameters (in a string property list)
    
     Name = Name of Weapon
     Damage = Damage Weapon does
     Bonus = Bonus of Weapon
     Number = The index number of the Weapon
   -->
   [h: num = getStrProp(macro.args, "Number")]
   [h: damage = getStrProp(macro.args, "Damage")]
   [h: name = getStrProp(macro.args, "Name")]
   [h: bonus = getStrProp(macro.args, "Bonus")]
   [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Name"), name)]
   [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Damage"), damage)]
   [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Bonus"), bonus)]

You can test this macro too by a little typing at the command line.

.. code:: mtmacro
   :number-lines:

   [macro("AddWeapon@Lib:Test"): "Number=1; Damage=1d8; Name=LongSword; Bonus=0"]

Look at the Weapons [Token_Property|property]] and see how its built up
our `string property list <Macros:string_property_list>`__ for us. It
wont have modified NumWeapons but that is ok we are going to assume that
NextWeaponNumber is always used before adding a new weapon. Before
clearing out the Weapons `property <Token_Property>`__ to reset it lets
write a function to retrieve a weapon.

Create a `macro button <Macro_Button>`__ called GetWeapon on your
`Lib:Test <Library_Token>`__ `Token <Token>`__ and paste the following
into it.

.. code:: mtmacro
   :number-lines:

   <!--
     Retrieves a weapon from the Weapons Property list.

     Parameters
       Weapon Number

     Returns
       A string property list with following keys
         Name = Name of Weapon
         Damage = Damage Weapon does
         Bonus = Bonus of Weapon
         Number = The index number of the Weapon
       If the weapon is not found then an empty string ("") is returned.
   -->
   [h: num = macro.args]
   [h: damage = getStrProp(Weapons, strformat("Weapon%{num}Damage"))]
   [h: name = getStrProp(Weapons, strformat("Weapon%{num}Name"))]
   [h: bonus = getStrProp(Weapons, strformat("Weapon%{num}Bonus"))]
   [h, if(name == ""):
      macro.return = ""
   ;
      macro.return = strformat("Number=%{num}; Damage=%{damage}; Bonus=%{bonus}; Name=%{name}")
   ]

Test it with

.. code:: mtmacro
   :number-lines:

   [h, macro("GetWeapon@Lib:Test"): 1] [macro.return]

Lets add a way to delete items. Create a `macro button <Macro_Button>`__
called DeleteWeapon and paste the following code.

.. code:: mtmacro
   :number-lines:

   <!-- ============================================================ -->
   <!-- ============================================================ -->
   <!-- ============================================================ -->
   <!--
     Deletes a weapon from the Weapons property List.

     Parameters
       The weapon number
   -->
   [h: num = macro.args]
   [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Damage"))]
   [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Name"))]
   [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Bonus"))]

One more "setup" function then we should be good to go. Lets create a
function that returns a `string list <Macros:string_list>`__ of all the
item numbers (remember we can have gaps because a user could cancel the
addition of the item after calling NextWeaponNumber or they could delete
a weapon). Create a `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ called GetWeaponNumbers

.. code:: mtmacro
   :number-lines:

   <!--
     Gets a string list of the valid weapon numbers
   -->
   <!-- If Weapons token property is empty set it to a default value -->
   [h,if(isPropertyEmpty("Weapons")): Weapons = "NumWeapons=0;"]

   [h: maxNum = getStrProp(Weapons, "NumWeapons")]
   [h: wnumList=""]
   [h,c(maxNum), code: {
     [h: wnum = roll.count+1]
     [h: name = getStrProp(Weapons, strformat("Weapon%{wnum}Name"))]
     [if(name != ""):
       wnumList = listAppend(string(wnumList), string(wnum))
     ]
   }]
   [h: macro.return = wnumList]

The `string() <Macros:Functions:string>`__ around the arguments in
`listAppend() <Macros:Functions:listAppend>`__ is to convert the
arguments to strings, as of b48
`listAppend() <Macros:Functions:listAppend>`__ seems to have problems
with arguments that could be interpreted as numbers.

.. _input_dialogs:

Input Dialogs
-------------

So now we can get back to the dialogs. Lets create a dialog to edit
weapons. Create a `macro button <Macro_Button>`__ on your
`Lib:Test <Library_Token>`__ called EditWeaponDialog and paste the
following into it.

.. code:: mtmacro
   :number-lines:

   [dialog("weaponInput"): {
     [h: weaponNum = getStrProp(macro.args, "Number")]
     [h: name = getStrProp(macro.args, "Name")]
     [h: bonus = getStrProp(macro.args, "Bonus")]
     [h: damage = getStrProp(macro.args, "Damage")]
     <!-- If we do not have a weapon number grab the next one -->
     [h, if(weaponNum == ""), code: {
       [h,macro("NextWeaponNumber@this"): ""]
       [h: weaponNum = macro.return]
     }]
     <html>
       <head>
         <title>Edit Weapon Dialog</title>
         <meta name="input" content="true">
       </head>
       <body>
         <form name="weaponInput" action="[r:macroLinkText('AddWeapon@Lib:Test')]">
           <table>
             <tr>
               <th>
                 <label for="Name">Weapon Name</label>
               </th>
               <td>
                 <input type="text" name="Name" value="[r: name]"></input> <br>
               </td>
             </tr>
             <tr>
               <th>
                 <label for="Damage">Weapon Damage</label>
               </th>
               <td>
                 <input type="text" name="Damage" value="[r: damage]"></input> <br>
               </td>
             </tr>
             <tr>
               <th>
                 <label for="Bonus">Weapon Bonus</label>
               </th>
               <td>
                 <input type="text" name="Bonus" value="[r: bonus]"></input>
               </td>
             </tr>
             </table>
           <!-- hidden input with the weapon number -->
           <input type="hidden" name="Number" value="[r: weaponNum]"></input>

           <input type="submit" name="Save" value="Save"> </input>
         </form>
       </body>
     </html>
   }]

`frame <image:EditWeaponDialog1.png>`__

One thing to note is @this will not work in a macro link, so we build
the @ portion of the macro to call when the form is submitted.

The action=... portion of the form tag specifies which macro to call
when any submit button is pushed for the form. If the dialog is
specified as a input dialog, the close button down the bottom is not
displayed and when any form on the dialog is submitted it is closed.

The arguments to the macro that is called when the form is submitted is
a string property list with the names of the input fields as the keys
and the entered value as the values. Since I named all my inputs the
same as the keys in the parameter for the AddWeaponMacro I can call that
straight from the submit action on the form (some times is seems like I
almost know what I am doing).

The only problem is our edit weapon is kinda plain compared to our
character sheet so time to add a little bling.

Change your EditWeaponDialog `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ to

.. code:: mtmacro
   :number-lines:

   [dialog("weaponInput"): {
     [h: weaponNum = getStrProp(macro.args, "Number")]
     [h: name = getStrProp(macro.args, "Name")]
     [h: bonus = getStrProp(macro.args, "Bonus")]
     [h: damage = getStrProp(macro.args, "Damage")]
     <!-- If we do not have a weapon number grab the next one -->
     [h, if(weaponNum == ""), code: {
       [h,macro("NextWeaponNumber@this"): ""]
       [h: weaponNum = macro.return]
     }]
     <html>
       <head>
         <title>Edit Weapon Dialog</title>
         <meta name="input" content="true">
         <link rel="stylesheet" type="text/css" href="EditWeapon_css@[r: getMacroLocation()]">
       </head>
       <body>
         <form name="weaponInput" action="[r:macroLinkText('AddWeapon@Lib:Test')]">
           <table>
             <tr>
               <td>
                 <table>
                   <tr>
                     <th>
                       <label for="Name">Weapon Name</label>
                     </th>
                     <td>
                       <input type="text" name="Name" value="[r: name]">
                       </input> <br>
                     </td>
                   </tr>
                   <tr>
                     <th>
                       <label for="Damage">Weapon Damage</label>
                     </th>
                     <td>
                       <input type="text" name="Damage" value="[r: damage]">
                       </input> <br>
                     </td>
                   </tr>
                   <tr>
                     <th>
                       <label for="Bonus">Weapon Bonus</label>
                     </th>
                     <td>
                       <input type="text" name="Bonus" value="[r: bonus]">
                       </input>
                     </td>
                   </tr>
                 </table>
               </td>
               <td>
                 <img src='[r: getTokenImage(100)]'></img>
               </td>
             </tr>
           </table>
           <!-- hidden input with the weapon number -->
           <input type="hidden" name="Number" value="[r: weaponNum]">
           </input>
           <input id="saveButton" type="submit" name="Save" value="Save">
           </input>
         </form>
       </body>
     </html>
   }]

And add `macro button <Macro_Button>`__ EditWeapon_css to
`Lib:Test <Library_Token>`__ that contains

.. code:: mtmacro
   :number-lines:

   body {
      background-color: #CCBBBB
   }

And you might as well add a AddWeapon `macro button <Macro_Button>`__ to
your `Token <Token>`__ that contains

.. code:: mtmacro
   :number-lines:

   [macro("EditWeaponDialog@Lib:Test"): "" ]
   [abort(0)]

Now our dialog looks like |EditWeaponDialog2.png|

Ok now lets make a quick dialog to display our weapons. Create a new
`macro button <Macro_Button>`__ on your `Lib:Test <Library_Token>`__
called ViewWeapons and paste in the following

.. code:: mtmacro
   :number-lines:

   [dialog("Weapons"): {
     <html>
       <head>
         <title>Weapons</title>
         <link rel="stylesheet" type="text/css" href="ViewWeapon_css@[r: getMacroLocation()]">
       </head>
       <body>
         [h,macro("GetWeaponNumbers@this"): ""]
         [h: wpList = macro.return]
         <table>
           [foreach(weapon, wpList, ""), code: {
             [h,macro("GetWeapon@this"): weapon]
             [h: wProp = macro.return]
             <tr class="WeaponName">
               <th>
                 [r: getStrProp(wProp, "Name")]
               </th>
             </tr>
             <tr>
               <th>Damage</th>
               <td>[r: getStrProp(wProp, "Damage")]</td>
               <th>Bonus</th>
               <td>[r: getStrProp(wProp, "Bonus")]</td>
             </tr>
           }]
         </table>
       </body>
     </html>
   }]

For good measure create a `macro button <Macro_Button>`__ called
ViewWeapon_css on `Lib:Test <Library_Token>`__ paste in the following.

.. code:: mtmacro
   :number-lines:

   .WeaponName {
       background-color: #55AA55;
       color: white;
       text-align: center;
   }

Add a `macro button <Macro_Button>`__ to your `Token <Token>`__ called
ViewWeapons which contains.

.. code:: mtmacro
   :number-lines:

   [macro("ViewWeapons@Lib:Test"): ""]
   [abort(0)]

And this is what it looks like. |ViewWeapons.png|

.. _creating_a_simple_character_sheet_frame:

Creating a Simple Character Sheet Frame
---------------------------------------

Up until now I havent talked at all about frames, but don't worry ,
change to above and it will work (except you cant have a frame that
closes when you submit a form, what would be the point?).

But lets make some final changes to show some frames, I am going to make
all of these in one go as everything in them has been discussed
previously in this post.

First we are going to completely change the CharSheet `macro
button <Macro_Button>`__ on `Lib:Test <Library_Token>`__ to

.. code:: mtmacro
   :number-lines:

   [frame("CharSheet"): {
     [h: page = getStrProp(macro.args, "Page")]
     [h,if(page==""): page="Main"]
     <html>
       <head>
         <title>Character Sheet</title>
         <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">
       </head>
       <body>
         [macro("CharSheetHeader@this"): page]
         <br>
         [macro("CharSheet"+page+"@this"): ""]
       </body>
     </html>
   }]

Create a CharSheetHeader `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ and paste the following into it.

.. code:: mtmacro
   :number-lines:

   [h: currentPage = macro.args]
   [h: pages = "Main,Weapons"]
   <table>
     <tr>
       [foreach(page, pages,""), code: {
         [h,if (page == currentPage): class="currentPage" ; class="page"]
         [h: callback = "CharSheet@"+getMacroLocation()]
         <td class="[r: class]">
           [r: macroLink(page, callback, "none", "Page="+page)]
         </td>
       }]
     </tr>
   </table>

Create a CharSheetMain `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ and paste the following into it.

.. code:: mtmacro
   :number-lines:

   [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]
   <table>
     <tr>
       <td>
         <img src='[r: getTokenImage(100)]'></img>
       </td>
       <td>
         <table id="stats">
           <tr>
             <th>Name</th>
             <th>Score</th>
           </tr>
           [h: class = "oddRow"]
           [foreach(prop, propNames, ""), code: {
             <tr class="[r:class]">
               <td>[r: prop]</td>
               <td>[r: getProperty(prop)]</td>
             </tr>
             [h: class = if(class=="oddRow", "evenRow", "oddRow")]
           }]
         </table>
       </td>
     </tr>
   </table>
   <hr>
   <table>
     <tr>
       <td>
         [h: hpBarArgs = strformat("MaxLen=50; Value=%{HP}; MaxValue=%{MaxHP}; Label=HP")]
         [macro("TrafficLightBar@this"): hpBarArgs]
       </td>
     </tr>
     <tr>
       <td>
         [h: hpBarArgs = strformat("MaxLen=50; Value=%{XP}; MaxValue=%{NextLevelXP}; Label=XP; Color=120,120,255")]
         [macro("StatusBar@this"): hpBarArgs]
       </td>
     </tr>
   </table>

Create a CharSheetWeapons `macro button <Macro_Button>`__ on
`Lib:Test <Library_Token>`__ and paste the following into it.

.. code:: mtmacro
   :number-lines:

   [h,macro("GetWeaponNumbers@this"): ""]
   [h: wpList = macro.return]
   <table>
     [foreach(weapon, wpList, ""), code: {
       [h,macro("GetWeapon@this"): weapon]
       [h: wProp = macro.return]
       <tr class="WeaponName">
         <th>
           [h: name = getStrProp(wProp, "Name")]
           [h: bonus = getStrProp(wProp, "Bonus")]
           [h: damage = getStrProp(wProp, "Damage")]
           [h: callback = "EditWeaponDialog@" + getMacroLocation()]
           [h: args = strformat("Number=%{weapon}; Name=%{name}; Damage=%{damage}; Bonus=%{bonus}")]
           [r: macroLink(name, callback, "none", args)]
         </th>
       </tr>
       <tr>
         <th>Damage</th>
         <td>[r: getStrProp(wProp, "Damage")]</td>
         <th>Bonus</th>
         <td>[r: getStrProp(wProp, "Bonus")]</td>
       </tr>
     }]
   </table>

And the last change to make is the CharSheet_css `macro
button <Macro_Button>`__ on `Lib:Test <Library_Token>`__ an paste the
following into it.

.. code:: mtmacro
   :number-lines:

   .oddRow { background-color: #FFFFFF }
   .evenRow { background-color: #EEEEAA }
   #stats th { background-color: #113311; color: #FFFFFF }
   .WeaponName a {
       background-color: #55AA55;
       color: white;
       text-align: center;
   }
   .page a {
      background-color: #5555CC;
      color: white;
   }
   .currentPage a {
      background-color: #7777FF;
      color: white;
   }

So what does this give us? A shiny new frame. Unlike Dialogs, Frames act
like any of the other maptool windows and can be docked on the sides, or
with other windows (forming a tab).

.. figure:: CharSheetFrame1.png
   :alt: CharSheetFrame1.png

   CharSheetFrame1.png

Where it says Main and Weapons on the top, they are links, if you click
on Weapons it will change the CharacerSheet frame to
|CharSheetFrame2.png|

And as an added bonus, the weapon names are links, if you click on them
it will open up the edit dialog where you can edit them. (note this will
not update the character sheet at this time, but that is left as an
exercise for the reader).

This has just been a short example of what can be done, I am sure people
will come up with some great ideas how to use this.

The campaign file with the dialogs we have created can be found at
`campaign <http://lmwcs.com/maptool/campaigns/B48MiniTuts.cmpgn>`__

.. _related_pages:

Related Pages
-------------

-  `Supported CSS Styles <Supported_CSS_Styles>`__
-  `Forms tutorial <Forms_tutorial>`__

`Category:Tutorial <Category:Tutorial>`__

.. |EditWeaponDialog2.png| image:: EditWeaponDialog2.png
.. |ViewWeapons.png| image:: ViewWeapons.png
.. |CharSheetFrame2.png| image:: CharSheetFrame2.png
