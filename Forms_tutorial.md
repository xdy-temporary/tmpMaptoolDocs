HTML forms covered in fish
==========================

*A tutorial to creating html forms for maptool.*

What is this about?
-------------------

The [input()](input "wikilink") function is a great way to get data from the user. Its simple to use as well. But it limits you in the ways you can design the resulting dialog. You might even miss features like multi-line textboxes. Maybe you want keep an dialog open to send it when you are ready, but still want the other maptool features to work - and not freeze.

If you can't create the user interaction with [input()](input "wikilink") you have to create a html form. And here I explain to you how to do that.

But be aware! A input pauses your macro, creates a pop up dialog and creates variables containing the entered data all by itself. With html forms you have to split the process in (at least) two macros and make all that by yourself.

I assume you know how to write simple macros and create/use lib:tokens. All my code examples will be located on a [lib:token](Library_Token "wikilink") named “Lib:token”.

**NOTE** I'm not the first one who tried to explain this. There is a nice tutorial on using html frames for creating a character sheet that covers even css embedding and tab page creation: [Introduction to Dialogs and Frames](Introduction_to_Dialogs_and_Frames "wikilink").

Where can you use forms?
------------------------

Maptool accepts html in uncountable places and theoretically where ever html is interpreted you could create a form. But really useful is it to place your html form either in a [dialog](dialog_(roll_option) "wikilink") or a [frame](frame_(roll_option) "wikilink"). A frame is a dockable window while a dialog is floating above the rest of the UI. A dialog has a close button as default while a frame has no buttons other than those you create there.

Both commands (or to be more specific: roll options) open some kind of window. Both frames and dialogs are named so when you use code that would open a window, it will update the content of an open window with the same name if that exists.

You can close dialogs in macro with [closeDialog()](closeDialog "wikilink") and in later versions you can close frames as well ([closeFrame()](closeFrame "wikilink")).

Lets create a macro “openFrame” so that we can display a form.

``` mtmacro
[frame("myForm"): {
    here will be a fishy form
}]
```

For my following examples we will use this slightly changed openFrame-macro:

``` mtmacro
[frame("myForm"): {
    <h3>my form:</h3>
    [r, macro("displayForm@Lib:token"): ""]
}]
```

And probably you can guess: all the form related code will be placed in a displayForm-macro. So we can forget about opening the frame and concentrate all on forms. Yay.

About forms
-----------

Now lets begin with that form. HTML supports user editable forms and a good variety of input fields that can be placed in such a form. A html page (your frame for example) can even contain multiple forms (but you'll only receive the content of one of them).

For general syntax information about the -tag and the input fields I find [w3schools.com](http://www.w3schools.com/html/html/forms.asp) quite helpful.

We begin at the start and create a form with two text input fields.

``` html4strict
<!-- this example displays correctly but does nothing -->
<form>
Character name: <input type="text" name="charName"><br>
Strength: <input type="text" name="str">
</form>
```

Note that you can place all possible html in such a form so you can easily design it any way you want. Create tables, use CSS, fonts, colors, ... **Maptool only supports HTML3.2 and [CSS1](Supported_CSS_Styles "wikilink")**. This is because the java controls being used in maptool don't support more recent versions of HTML/CSS. Dont blame maptool ;)

While this is pretty handy you don't get the data your user enters yet. First we dont have a submit button and second maptool doesnt know where to send that data.

If we do it right a form - if submitted - calls another macro, lets call that 'processForm', and passes the entered data as macro.args. You can receive this data as string property list or as json which I prefer. If you prefer string property lists you have to omit the method field of the form tag (and change the processForm-macros).

We specify the called macro using [macroLinkText()](macroLinkText "wikilink"). You should not specify the macro.args here as it will interfere with the form data.

Now lets make my little form work:

``` mtmacro
[h: processorLink = macroLinkText("processForm@Lib:token", "all")]
<form action="[r:processorLink]" method="json">
Character name: <input type="text" name="charName"><br>
Strength: <input type="text" name="str"><br>
<input type="submit" name="myForm_btn" value="Okay">
</form>
```

And create the processForm-macro.

``` mtmacro
<pre>
[r: json.indent(macro.args,2)]
</pre>
```

With this setup we can very easily find out how a specific form packs the data entered and how we could work with that. For this tutorial this processForm-macro will do.

The output we receive from this example is

``` mtmacro
{
  "charName": "the fishy dude",
  "str": "7",
  "myForm_btn": "Okay"
}
```

Now its pretty easy to access the name and strength using [json.get()](json.get "wikilink").

The input fields
----------------

Now let me introduce you to the input fields in detail. Some are a little tricky in how they send their data - so there will be advice about that as well.

In general all input fields should be given a name. This name will be used in the resulting json data as key.

<image:Cif_forms_tutorial_example_input_fields.png>

### Text fields

``` html4strict
<input type="text" name="" size="" maxlength="" value="">
```

This is your standard one line text input field. The width of the field can be set with and the maximum length of the input with . If you set a your field will appear filled with that.

You can have a password type text field as well if you set

``` html4strict
<input type="password" name="" size="" maxlength="" value="">
```

### Multi line text fields

If you need multiple lines you use

``` html4strict
<textarea name="" cols="" rows="">
Enter your text here...
</textarea>
```

You can specifiy the size of that text box with and . A preset text would be written between the open and closing tags.

**TRICK:** You can process the content of a textarea line by line if you use the following trick. By using [encode()](encode "wikilink") on the complete content you change line breaks into . Then you can use string list functions using as separator.

As example let me show you a processForm macro that adds all numbers you enter in the textarea - one number per line. Dice expressionsare evaluated.

``` mtmacro
<!-- processForm -->
[h: formData = macro.args]
<!-- get the content of a textarea named "textarea" -->
[h: text = json.get(formData, "textarea")]
<!-- encode it -->
[h: text = encode(text)]
<!-- loop through the content -->
[h: sum=0]
[h, foreach(line, text, "", "%0A"), code: {
    <!-- decode line again -->
    [h: decodedLine = decode(line)]
    [h, if(isNumber(decodedLine):
        sum = sum + decodedLine;
        sum = sum + eval(decodedLine)
    ]
}]
<!-- and output. done. -->
[r: sum]
```

### Drop down lists

``` html4strict
<select name="" size="">
    <option>A</option>
    <option>B</option>
    <option selected="selected">C</option>
</select>
```

**NOTE** doesnt work, only one entry appears in the resulting json. Known bug.

### Radio buttons

``` html4strict
A<input type="radio" name="group1" value="A" checked="checked">
B<input type="radio" name="group1" value="B">
C<input type="radio" name="group1" value="C">

A<input type="radio" name="group2" value="A" checked="checked">
B<input type="radio" name="group2" value="B">
C<input type="radio" name="group2" value="C">
```

### Checkboxes

``` html4strict
<input type="checkbox" name="group1" value="A"> A
<input type="checkbox" name="group1" value="B"> B
<input type="checkbox" name="group1" value="C"> C
<input type="checkbox" name="group1" value="D" checked="checked"> D
```

**NOTE** unchecked boxes don't appear in the json; only checked ones will. So test if a box is checked by using on the field name.

See my [“Good advice” tip \#4](Forms_tutorial#Predefine_checkboxes "wikilink") for another way to treat this (you can predefine the value with a 0-value).

**NOTE** multiple selection doesnt work as well. So do not name the checkboxes alike.

### Hidden data

``` html4strict
<input type="hidden" name="" value="">
```

Since you cannot send additional information to your form processor using the args parameter of you have to send it piggyback with the form data. This can be done with invisible fields.

### Buttons

``` html4strict
<input type="submit" name="" value="">
```

The button caption is set via the parameter.

**NOTE** only the pressed button appears in the json. If you use multiple buttons use [json.contains()](json.contains "wikilink") to identify it. Predefining the key/name could probably help (see checkboxes).

**NOTE** You can use **html formatting** inside of the button caption (value parameter). You have to enable this by beginning with like this:

``` mtmacro

<input type="submit" value="<html><b>Button</b></html>">
```

You can't apply any kind of CSS to html inputs. To remove the html tags from the submitted value you can use code like this

``` mtmacro

[H: submit = json.get(macro.args,"submit")]
[H: submit = replace(submit,"<[^>]*?>","")]
```

### Image buttons

First you have to get the asset of the image you want to place on a button. Good ways to do so is by using an image table or image tokens. I wont explain that here in more detail.

``` html4strict
<input type="image" src="" name="" value="">
```

This image button submits the form exactly as a submit button does. As you have to set an image asset. Note that you cannot used resized assets (using the ASSETxSIZE notation or specifying the size on asset generating function calls).

It does not only send the button name and value but also the coordinates where you clicked in the image. This could be used for some pretty UI.

``` mtmacro
<!-- this image button pushed .. -->

<input type="image" src="[r:getImage("Image:Attack")]" name="img_btn" value="image button clicked">

<!-- .. would send this args -->
{
    "img_btn.value": "image button clicked",
    "img_btn.x": "21",
    "img_btn.y": "13"
}
```

Events
------

Since I'll use this in one of my examples (see below) let me very shortly introduce you some kind of event maptool supports and how to set it up. A discussion about this can be found in the [maptool forums](http://forums.rptools.net/viewtopic.php?p=143242#p143242) and a list of events on the [:Category:Event](:Category:Event "wikilink") page.

Maptool macros can react on three events: if a token is changed, if token selection is changed and if impersonation is changed. You can specifiy a macro that is called if one event happens.

This will work if a frame is open at that moment. The onChangeToken-event is a little bit tricky. First it is fired numerous times and not only if you'd expect it. Second is your macro can change tokens and so fire the event and call itself… what could cause problems.

The other two events are pretty easy to use and quite handy for dumping informations about selected tokens and such.

To set it up you have to define a html header and specify a specific link element. So your frame content should begin like this:

``` html4strict
<html>
<head>
  <link rel='onChangeSelection' type='macro' href='macroLink'>
</head>
<body>
```

Replace by an actual macroLinkText-call to a macro of your choice. A common practice is to call the frame opening macro itself to actualize the content. the parameter is set either , or .

Good advice
-----------

### Always encode user input

It is always wise to trust in the dumbness of users. If they can break things they will. And i dont say they do it intentionally.

So you should protect your macros against trouble making user inputs. For example can a comma inside of an item of a comma separated list break the list.

So its always always good to use [encode()](encode "wikilink") on user input (and [decode()](decode "wikilink") to .. well .. decode it again).

### Building complex html forms can take time

Just be aware of this. Building and rendering html and collecting and displaying lots of data and images and fields can take serious time. If your frame is updated frequently it could cause speed issues.

Think about storing calculated frame content, only updating the necessary parts. Reduce the number of updates to the needed minimum. (See Caching)

Dont make things complicated if you do not have speed issues but be prepared to fight them if you do.

### Caching html forms

Since building html forms can take serious amounts of time its a good practice to store build form html in a token property and reuse it as long it doesnt have to be rebuild. Its especially effective if you build complex stuff by accessing lots of property - usually the case if you build character sheets. When creating complex html structures and storing them into a token property you're asking for trouble so its common practice to encode them first before you store them. It's also best to store character sheets (token specific) onto the (n)pc token and general forms like weapon list, skill list, etc. onto a lib:token

Here an example of 'caching' a charactersheet.

``` mtmacro
[h: rebuild = macro.args]
[h: id = currentToken()]
[h: output = getProperty("charSheetCache", id)]

[h, if(rebuild || output == ""), code: {
    [h: output = "here you build"]
    [h: output = output + "your mega complex character sheet"]
    ...
    [h: output = encode(output)]

    [h:'<!-- though it might be better to define a UDF for that -->']
    [h:'<!-- e.g: output = encode(createSheetContent()) -->']

    [h: setProperty("charSheetCache", output, id)]
};{}]

[frame("Character Sheet"):{
    [r: decode(output)]
}]
```

A nice technique to individualize cached forms/html is described here: [Making cached structures dynamic (Load BIG forms FAST)](http://forums.rptools.net/viewtopic.php?f=20&t=16324&start=0)

### Don't forget the token context

When you work with macrolinks you can easily lose the token context. If you happen to work with explicit ids and get/setProperty() a lot that may be no problem for you.

However it does change the chat output. If a macrolink is called with unknown token context instead of token image and name the chat line begins with user name.

If you dont like this always specify the token context in your and calls.

An example of this can be found in the [forum](http://forums.rptools.net/viewtopic.php?p=170425#p170425).

### Predefine checkboxes

Checkboxes only create data in macro.args if they are checked. There is a neat trick to always create the relevant data even if it is unchecked. Predefine the key/value-pair using a hidden input with a 0 (of course you have to use the same name as your checkbox has). A checked checkbox will overwrite a predefined 0 while a unchecked checkbox (as it does not generate anything) won't overwrite a predefined 1.

If you want to have a initially checked checkbox you can set it as checked like this (regardless of beeing predefined or not)

``` html4strict
<input type="checkbox" name="surprised"  value="1" checked="checked" />
```

Big thanks to wolph42 for learning me this.

### Don't shy away from layout tables

In webdesign layout tables might be a no-go. Don't be afraid of them in maptool. They are a great way to precisly align your form elements. Let me demonstrate how different a simple layout table looks compared to a very simplistic inline approach.

![Image:Cif forms tutorial example layout table.png](Cif_forms_tutorial_example_layout_table.png "Image:Cif forms tutorial example layout table.png")

``` mtmacro
[frame("test"): {

<h3>this is ugly</h3>
Value <input type="text" size="5" /><br>
Option1<input type="checkbox" /><br>
Option2<input type="checkbox" /><br>
<input type="submit"><br>

<h3>this is pretty</h3>
<table>
<tr>
   <td>Value</td>
   <td><input type="text" size="5" /></td>
</tr>
<tr>
   <td>Option1</td>
   <td><input type="checkbox" /></td>
</tr>
<tr>
   <td>Option2</td>
   </td><input type="checkbox" />
</td>
<tr>
   <td colspan="2"><input type="submit" /></td>
</tr>
</table>

}]
```

The big examples
----------------

### Character sheet/editor

Lets create an character sheet and editor for the [maptool sample ruleset](Sample_Ruleset "wikilink") using what we learned so far.

<image:Cif_forms_tutorial_screenshot_example1.png>

First we need a frame. We want it to auto-update with the selected content. We pass the selected tokens to the character sheet generating macro so we know what do display.

We want more eyecandy, so we will use css. As we like separating css rules from the content we will place it in its own macro.

**openCharacterSheet**

``` mtmacro
[h: link = macroLinkText("openCharacterSheet@Lib:token", "none")]
[frame("csheet"): {
<html>
<head>
<link rel="onChangeSelection" type="macro" href="[r:link]">
<link rel="stylesheet" type="text/css" href="css@Lib:token"></link>
</head>
<body>
[r, macro("characterSheet@Lib:token"): getSelected()]
</body>
</html>
}]
```

**css**

``` css
.odd { background-color: #FFFFFF }
.even { background-color: #EEEEAA }
th { background-color: #113311; color: #FFFFFF }
```

Then we have to actually build the character sheet. Since selection will cause this to be called we have to deal with empty and multiple selections. We'll just don't create any output then.

**characterSheet**

``` mtmacro
[h: id = macro.args]
[r, if(listCount(id)!=1), code: {};{

[h: link = macroLinkText("editCharacterSheet@Lib:token", "all")]
<form action="[r:link]" method="json">
 <input type="hidden" name="id" value="[r:id]">
<h1>[r:getName(id)]</h1>

<table width="*">
<tr>
  <th colspan="2">Primary Attributes</th>
</tr>

[h: attributes = "Strength, Dexterity, Intelligence, Endurance"]
[h: row = "odd"]
[r, foreach(attrib, attributes, ""), code: {
    <tr class="[r:row]">
    <td><b>[r:attrib]:</b></td>
    <td><input type="text" name="[r:attrib]" value="[r:getProperty(attrib, id)]" size="3" align="right"></td>
    </tr>
    [h: row = if(row=="odd", "even", "odd")]
}]

<tr>
  <th colspan="2">Secondary Attributes</th>
</tr>
[h: attributes = "Hit Points, Armor, Movement"]
[h: row = "odd"]
[r, foreach(attrib, attributes, ""), code: {
    <tr class="[r:row]">
    <td><b>[r:attrib]:</b></td>
    <td>[r:getProperty(attrib, id)]</td>
    </tr>
    [h: row = if(row=="odd", "even", "odd")]
}]
[h: classes = "Warrior, Rogue, Wizard, Priest"]
[h: CharClass = getProperty("CharClass", id)]
<tr class="[r:row]">
    <td><b>Class:</b></td>
    <td>
        <select name="CharClass" size="1">
        [r, foreach(c, classes, ""), code: {
            <option [r, if(c==CharClass): "selected"]>[r:c]</option>
        }]
    </select>
    </td>
</tr>

<input type="submit" name="edit_btn" value="Submit changes">
</form>
}]
```

If the submit button is pressed we want to save the changes back to the token.

**editCharacterSheet**

``` mtmacro
[h: arguments = macro.args]
[h: id = json.get(arguments, "id")]

<!-- set primary attributes -->
[h: attributes = "Strength, Dexterity, Intelligence, Endurance"]
[h, foreach(attrib, attributes), code: {
    [h: val = json.get(macro.args, attrib)]
    [h, if(! isNumber(val)): val=eval(val)]
    <!-- allowed values are 1..6 -->
    [h: val = min(max(val,1), 6)]
    [r: setProperty(attrib, val, id)]
}]

[h: setProperty("Hit Points", 6*getProperty("Endurance",id), id)]
[h: setProperty("Class", json.get(macro.args, "CharClass"), id)]
[h: setProperty("Movement", getProperty("Dexterity",id), id)]


[h: CharClass = getProperty("CharClass", id)]





[h, switch(CharClass):
    case "Warrior": val=6;
    case "Rogue": val=2;
    case "Wizard": val=1;
    case "Priest": val=4;
   default: val=0
]
[h: setProperty("Armor", val, id)]

[h: setProperty("Hit Points", 6*getProperty("Endurance",id), id)]

Changes saved to [r: getName(id)].
[h, macro("openCharacterSheet@Lib:token"): id]
```

If you'd want to play with this you'd surely come up with lots of improvements .. great! I would as well. But this should be enough to demonstrate building a character sheet or editor with html forms.

**Download** this example:[example1.rptok](http://www.bastian-dornauf.de/example1.rptok)(token is saved with b73) Drop this libtoken into an empty map and toy around with it.

### Click-based Target selection

There are very differen ways how to select targets of an action. The clickbased targeting (first done by Rumble) works best in maptool version b70 or later with the “unowned selection” feature.

<image:Cif_forms_tutorial_screenshot_example2.png>

You impersonate or select the active token. Then you execute a macro, eg “Attack” that opens a frame. In that frame you can enter additional infos like modifier. While that frame is open you select ((with the mouse on the map)) the target(s) of the attack. The frame has a button that actually performs the attack.

Lets start with the macro that opens that frame.

**openActionFrame**

This macro first determines what token should be considered the *active* token. A token impersonated would be preferred. Otherwise the selection is taken. If no or multiple tokens are selected the macro us aborted.

Then the macro checks if the user has the right to perform actions with that token - he has if he is GM or own the token.

After that the current selection is cleared and the frame displaying code is called.

If you have different actions to perform here would the place to branch into different actionFrames according to the chosen action.

``` mtmacro
[h: chosenAction = macro.args]
[h, if(hasImpersonated()): activeId = getImpersonated(); activeId = getSelected()]
[h, if(listCount(activeId)!=1): assert(0, "You have to select only one token")]
[h: gm = isGM()]
[h: owned = isOwner(getPlayerName(), activeId)]
[h, if(gm ||  owned): ""; assert(0, "You have no right to act with this token.")]
[h: deselectTokens()]

<!-- call right actionFrame for chosenAction -->
[r, macro("actionFrame@Lib:tkn"): activeId]
```

Now we need a way for the user to call this macro. This can be either a campaign or a token macro - depending on your taste.

**Attack**

``` mtmacro
[r, macro("openActionFrame@Lib:token"):"Attack"]
```

*Note* that I send to the frame opening macro and that this is placed in a variable named . It is never used. If you want to support different actions (like ranged and melee attacks) you could, right after the comment, branch - depending on - into different actionFrame.

**actionFrame** This is pretty simple. It shows a frame and uses the -event to display the targets.

``` mtmacro
[h: activeId = macro.args]
[h: selection = getSelected()]
[h: link = macroLinkText("actionFrame@Lib:tkn", "none", activeId)]
[h: perform= macroLinkText("performAction@Lib:tkn", "all")]
[frame("Action"): {
<html>
<head>
<link rel='onChangeSelection' type='macro' href='[r:link]'>
</head>
<body>
<b>Attacker:</b><br>
[r, token(activeId): strformat("<img src='%s' alt='%s'>", getTokenImage(50), getName())]
<br>
<b>Targets:</b> <br>
[r, foreach(id, selection, " "), code: {
[r, token(id): strformat("<img src='%s' alt='%s'>", getTokenImage(50), getName())]
}]
<form action="[r:perform]" method="json">
<input type="text" name="mods" value="0"><br>
<input type="submit" name="btn_submit" value="Perform action">
<input type="hidden" name="id" value="[r:activeId]">
<input type="hidden" name="targets" value="[r:selection]">
}]
```

**performAction**

``` mtmacro
[h: arguments = macro.args]
[h: id = json.get(arguments, "id")]
[h: targets = json.get(arguments, "targets")]
[h, if(listCount(targets)<1): abort(0)]
<!-- target and performer could be the same -->
<!-- target could be one or many -->

<!-- roll the attack -->
<b>Melee attack:</b><br>
[r, foreach(target, targets, "<br>"), code: {
    <b>[r: getName(id)]</b> rolls
    [r, token(id): rollResult = 1d20 + Strength]
    [r, if(rollResult>=15), code: {
        and hits <b>[r:getName(target)]</b> for
        [r: dmg = 1d6 + getProperty("Strength", id) - getProperty("Armor", target)]
        points of damage.
        [h: setProperty("Hit Points", getProperty("Hit Points", target) - max(0,dmg), target)]
    };{and misses [r:getName(target)]}]
}]
```

This macro does the actual attack. The attacker and the targets are submitted via . The rest is the usual dice rolling and comparing to target numbers and stuff...

Again this could be done better. It doesnt modify the roll by the entered mods. It does not even model the sample ruleset right. You'd want to support attack powers and maybe set states for being wounded or dead.

But it demonstrates how to target .. the rest is up to you.

**Download** a lib token for this example [example2.rptok](http://www.bastian-dornauf.de/example2.rptok) (token is saved with b73)

<Category:Tutorial>