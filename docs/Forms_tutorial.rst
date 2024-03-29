===========================
Forms tutorial - MapToolDoc
===========================

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

   .. rubric:: Forms tutorial
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

         | 

         .. container:: template_advanced

            ADVANCED
            THIS IS AN ADVANCED ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 HTML forms covered in
               fish <#HTML_forms_covered_in_fish>`__

               -  `1.1 What is this about? <#What_is_this_about.3F>`__
               -  `1.2 Where can you use
                  forms? <#Where_can_you_use_forms.3F>`__
               -  `1.3 About forms <#About_forms>`__
               -  `1.4 The input fields <#The_input_fields>`__

                  -  `1.4.1 Text fields <#Text_fields>`__
                  -  `1.4.2 Multi line text
                     fields <#Multi_line_text_fields>`__
                  -  `1.4.3 Drop down lists <#Drop_down_lists>`__
                  -  `1.4.4 Radio buttons <#Radio_buttons>`__
                  -  `1.4.5 Checkboxes <#Checkboxes>`__
                  -  `1.4.6 Hidden data <#Hidden_data>`__
                  -  `1.4.7 Buttons <#Buttons>`__
                  -  `1.4.8 Image buttons <#Image_buttons>`__

               -  `1.5 Events <#Events>`__
               -  `1.6 Good advice <#Good_advice>`__

                  -  `1.6.1 Always encode user
                     input <#Always_encode_user_input>`__
                  -  `1.6.2 Building complex html forms can take
                     time <#Building_complex_html_forms_can_take_time>`__
                  -  `1.6.3 Caching html forms <#Caching_html_forms>`__
                  -  `1.6.4 Don't forget the token
                     context <#Don.27t_forget_the_token_context>`__
                  -  `1.6.5 Predefine
                     checkboxes <#Predefine_checkboxes>`__
                  -  `1.6.6 Don't shy away from layout
                     tables <#Don.27t_shy_away_from_layout_tables>`__

               -  `1.7 The big examples <#The_big_examples>`__

                  -  `1.7.1 Character
                     sheet/editor <#Character_sheet.2Feditor>`__
                  -  `1.7.2 Click-based Target
                     selection <#Click-based_Target_selection>`__

         .. rubric:: HTML forms covered in fish
            :name: html-forms-covered-in-fish

         *A tutorial to creating html forms for maptool.*

         .. rubric:: What is this about?
            :name: what-is-this-about

         The `input() <input>`__ function is a great way
         to get data from the user. Its simple to use as well. But it
         limits you in the ways you can design the resulting dialog. You
         might even miss features like multi-line textboxes. Maybe you
         want keep an dialog open to send it when you are ready, but
         still want the other maptool features to work - and not freeze.

         If you can't create the user interaction with
         `input() <input>`__ you have to create a html
         form. And here I explain to you how to do that.

         But be aware! A input pauses your macro, creates a pop up
         dialog and creates variables containing the entered data all by
         itself. With html forms you have to split the process in (at
         least) two macros and make all that by yourself.

         I assume you know how to write simple macros and create/use
         lib:tokens. All my code examples will be located on a
         `lib:token <Library_Token>`__ named "Lib:token".

         **NOTE** I'm not the first one who tried to explain this. There
         is a nice tutorial on using html frames for creating a
         character sheet that covers even css embedding and tab page
         creation: `Introduction to Dialogs and
         Frames <Introduction_to_Dialogs_and_Frames>`__.

         .. rubric:: Where can you use forms?
            :name: where-can-you-use-forms

         Maptool accepts html in uncountable places and theoretically
         where ever html is interpreted you could create a form. But
         really useful is it to place your html form either in a
         `dialog <dialog_(roll_option)>`__ or a
         `frame <frame_(roll_option)>`__. A frame is a
         dockable window while a dialog is floating above the rest of
         the UI. A dialog has a close button as default while a frame
         has no buttons other than those you create there.

         Both commands (or to be more specific: roll options) open some
         kind of window. Both frames and dialogs are named so when you
         use code that would open a window, it will update the content
         of an open window with the same name if that exists.

         You can close dialogs in macro with
         `closeDialog() <closeDialog>`__ and in later
         versions you can close frames as well
         (`closeFrame() <closeFrame>`__).

         Lets create a macro "openFrame" so that we can display a form.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("myForm"): {

               #. .. code-block:: none

                         here will be a fishy form

               #. .. code-block:: none

                     }]

         For my following examples we will use this slightly changed
         openFrame-macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("myForm"): {

               #. .. code-block:: none

                         <h3>my form:</h3>

               #. .. code-block:: none

                         [r, macro("displayForm@Lib:token"): ""]

               #. .. code-block:: none

                     }]

         And probably you can guess: all the form related code will be
         placed in a displayForm-macro. So we can forget about opening
         the frame and concentrate all on forms. Yay.

         .. rubric:: About forms
            :name: about-forms

         Now lets begin with that form. HTML supports user editable
         forms and a good variety of input fields that can be placed in
         such a form. A html page (your frame for example) can even
         contain multiple forms (but you'll only receive the content of
         one of them).

         For general syntax information about the ``<form>``-tag and the
         input fields I find
         [`w3schools.com <http://www.w3schools.com/html/html/forms.asp>`__]
         quite helpful.

         We begin at the start and create a form with two text input
         fields.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <!-- this example displays correctly but does nothing -->

               #. .. code-block:: none

                     <form>

               #. .. code-block:: none

                     Character name: <input type="text" name="charName"><br>

               #. .. code-block:: none

                     Strength: <input type="text" name="str">

               #. .. code:: de2

                     </form>

         Note that you can place all possible html in such a form so you
         can easily design it any way you want. Create tables, use CSS,
         fonts, colors, ... **Maptool only supports HTML3.2
         and**\ `CSS1 <Supported_CSS_Styles>`__. This is
         because the java controls being used in maptool don't support
         more recent versions of HTML/CSS. Dont blame maptool ;)

         While this is pretty handy you don't get the data your user
         enters yet. First we dont have a submit button and second
         maptool doesnt know where to send that data.

         If we do it right a form - if submitted - calls another macro,
         lets call that 'processForm', and passes the entered data as
         macro.args. You can receive this data as string property list
         or as json which I prefer. If you prefer string property lists
         you have to omit the method field of the form tag (and change
         the processForm-macros).

         We specify the called macro using
         `macroLinkText() <macroLinkText>`__. You should
         not specify the macro.args here as it will interfere with the
         form data.

         Now lets make my little form work:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: processorLink = macroLinkText("processForm@Lib:token", "all")]

               #. .. code-block:: none

                     <form action="[r:processorLink]" method="json">

               #. .. code-block:: none

                     Character name: <input type="text" name="charName"><br>

               #. .. code-block:: none

                     Strength: <input type="text" name="str"><br>

               #. .. code:: de2

                     <input type="submit" name="myForm_btn" value="Okay">

               #. .. code-block:: none

                     </form>

         And create the processForm-macro.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <pre>

               #. .. code-block:: none

                     [r: json.indent(macro.args,2)]

               #. .. code-block:: none

                     </pre>

         With this setup we can very easily find out how a specific form
         packs the data entered and how we could work with that. For
         this tutorial this processForm-macro will do.

         The output we receive from this example is

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                       "charName": "the fishy dude",

               #. .. code-block:: none

                       "str": "7",

               #. .. code-block:: none

                       "myForm_btn": "Okay"

               #. .. code:: de2

                     }

         Now its pretty easy to access the name and strength using
         `json.get() <json.get>`__.

         .. rubric:: The input fields
            :name: the-input-fields

         Now let me introduce you to the input fields in detail. Some
         are a little tricky in how they send their data - so there will
         be advice about that as well.

         In general all input fields should be given a name. This name
         will be used in the resulting json data as key.

         |Cif forms tutorial example input fields.png|

         .. rubric:: Text fields
            :name: text-fields

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="text" name="" size="" maxlength="" value="">

         This is your standard one line text input field. The width of
         the field can be set with ``size`` and the maximum length of
         the input with ``maxlength``. If you set a ``value`` your field
         will appear filled with that.

         You can have a password type text field as well if you set

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="password" name="" size="" maxlength="" value="">

         .. rubric:: Multi line text fields
            :name: multi-line-text-fields

         If you need multiple lines you use

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <textarea name="" cols="" rows="">

               #. .. code-block:: none

                     Enter your text here...

               #. .. code-block:: none

                     </textarea>

         You can specifiy the size of that text box with ``cols`` and
         ``rows``. A preset text would be written between the open and
         closing tags.

         **TRICK:** You can process the content of a textarea line by
         line if you use the following trick. By using
         `encode() <encode>`__ on the complete content you
         change line breaks into ``%0A``. Then you can use string list
         functions using ``%0A`` as separator.

         As example let me show you a processForm macro that adds all
         numbers you enter in the textarea - one number per line. Dice
         expressionsare evaluated.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- processForm -->

               #. .. code-block:: none

                     [h: formData = macro.args]

               #. .. code-block:: none

                     <!-- get the content of a textarea named "textarea" -->

               #. .. code-block:: none

                     [h: text = json.get(formData, "textarea")]

               #. .. code:: de2

                     <!-- encode it -->

               #. .. code-block:: none

                     [h: text = encode(text)]

               #. .. code-block:: none

                     <!-- loop through the content -->

               #. .. code-block:: none

                     [h: sum=0]

               #. .. code-block:: none

                     [h, foreach(line, text, "", "%0A"), code: {

               #. .. code:: de2

                         <!-- decode line again -->

               #. .. code-block:: none

                         [h: decodedLine = decode(line)]

               #. .. code-block:: none

                         [h, if(isNumber(decodedLine):

               #. .. code-block:: none

                             sum = sum + decodedLine;

               #. .. code-block:: none

                             sum = sum + eval(decodedLine)

               #. .. code:: de2

                         ]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     <!-- and output. done. -->

               #. .. code-block:: none

                     [r: sum]

         .. rubric:: Drop down lists
            :name: drop-down-lists

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <select name="" size="">

               #. .. code-block:: none

                         <option>A</option>

               #. .. code-block:: none

                         <option>B</option>

               #. .. code-block:: none

                         <option selected="selected">C</option>

               #. .. code:: de2

                     </select>

         **NOTE** ``multiple`` doesnt work, only one entry appears in
         the resulting json. Known bug.

         .. rubric:: Radio buttons
            :name: radio-buttons

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     A<input type="radio" name="group1" value="A" checked="checked">

               #. .. code-block:: none

                     B<input type="radio" name="group1" value="B">

               #. .. code-block:: none

                     C<input type="radio" name="group1" value="C">

               #. .. code-block:: none

                      

               #. .. code:: de2

                     A<input type="radio" name="group2" value="A" checked="checked">

               #. .. code-block:: none

                     B<input type="radio" name="group2" value="B">

               #. .. code-block:: none

                     C<input type="radio" name="group2" value="C">

         .. rubric:: Checkboxes
            :name: checkboxes

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="checkbox" name="group1" value="A"> A

               #. .. code-block:: none

                     <input type="checkbox" name="group1" value="B"> B

               #. .. code-block:: none

                     <input type="checkbox" name="group1" value="C"> C

               #. .. code-block:: none

                     <input type="checkbox" name="group1" value="D" checked="checked"> D

         **NOTE** unchecked boxes don't appear in the json; only checked
         ones will. So test if a box is checked by using
         ``json.contains`` on the field name.

         See my `"Good advice" tip
         #4 <Forms_tutorial#Predefine_checkboxes>`__ for
         another way to treat this (you can predefine the value with a
         0-value).

         **NOTE** multiple selection doesnt work as well. So do not name
         the checkboxes alike.

         .. rubric:: Hidden data
            :name: hidden-data

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="hidden" name="" value="">

         Since you cannot send additional information to your form
         processor using the args parameter of ``macroLinkText`` you
         have to send it piggyback with the form data. This can be done
         with invisible fields.

         .. rubric:: Buttons
            :name: buttons

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="submit" name="" value="">

         The button caption is set via the ``value`` parameter.

         **NOTE** only the pressed button appears in the json. If you
         use multiple buttons use
         `json.contains() <json.contains>`__ to identify
         it. Predefining the key/name could probably help (see
         checkboxes).

         **NOTE** You can use **html formatting** inside of the button
         caption (value parameter). You have to enable this by beginning
         with ``<html>`` like this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  <input type="submit" value="<html><b>Button</b></html>">

         You can't apply any kind of CSS to html inputs. To remove the
         html tags from the submitted value you can use code like this

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [H: submit = json.get(macro.args,"submit")]

               #. .. code-block:: none

                     [H: submit = replace(submit,"<[^>]*?>","")]

         .. rubric:: Image buttons
            :name: image-buttons

         First you have to get the asset of the image you want to place
         on a button. Good ways to do so is by using an image table or
         image tokens. I wont explain that here in more detail.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="image" src="" name="" value="">

         This image button submits the form exactly as a submit button
         does. As ``src`` you have to set an image asset. Note that you
         cannot used resized assets (using the ASSETxSIZE notation or
         specifying the size on asset generating function calls).

         It does not only send the button name and value but also the
         coordinates where you clicked in the image. This could be used
         for some pretty UI.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- this image button pushed .. -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <input type="image" src="[r:getImage("Image:Attack")]" name="img_btn" value="image button clicked">

               #. .. code-block:: none

                      

               #. .. code:: de2

                     <!-- .. would send this args -->

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         "img_btn.value": "image button clicked",

               #. .. code-block:: none

                         "img_btn.x": "21",

               #. .. code-block:: none

                         "img_btn.y": "13"

               #. .. code:: de2

                     }

         .. rubric:: Events
            :name: events

         Since I'll use this in one of my examples (see below) let me
         very shortly introduce you some kind of event maptool supports
         and how to set it up. A discussion about this can be found in
         the `maptool
         forums <http://forums.rptools.net/viewtopic.php?p=143242#p143242>`__
         and a list of events on the
         `Category:Event <Category:Event>`__ page.

         Maptool macros can react on three events: if a token is
         changed, if token selection is changed and if impersonation is
         changed. You can specifiy a macro that is called if one event
         happens.

         This will work if a frame is open at that moment. The
         onChangeToken-event is a little bit tricky. First it is fired
         numerous times and not only if you'd expect it. Second is your
         macro can change tokens and so fire the event and call itself…
         what could cause problems.

         The other two events are pretty easy to use and quite handy for
         dumping informations about selected tokens and such.

         To set it up you have to define a html header and specify a
         specific link element. So your frame content should begin like
         this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <html>

               #. .. code-block:: none

                     <head>

               #. .. code-block:: none

                       <link rel='onChangeSelection' type='macro' href='macroLink'>

               #. .. code-block:: none

                     </head>

               #. .. code:: de2

                     <body>

         Replace ``macroLink`` by an actual macroLinkText-call to a
         macro of your choice. A common practice is to call the frame
         opening macro itself to actualize the content. the ``rel``
         parameter is set either ``onChangeSelection``,
         ``onChangeImpersonated`` or ``onChangeToken``.

         .. rubric:: Good advice
            :name: good-advice

         .. rubric:: Always encode user input
            :name: always-encode-user-input

         It is always wise to trust in the dumbness of users. If they
         can break things they will. And i dont say they do it
         intentionally.

         So you should protect your macros against trouble making user
         inputs. For example can a comma inside of an item of a comma
         separated list break the list.

         So its always always good to use
         `encode() <encode>`__ on user input (and
         `decode() <decode>`__ to .. well .. decode it
         again).

         .. rubric:: Building complex html forms can take time
            :name: building-complex-html-forms-can-take-time

         Just be aware of this. Building and rendering html and
         collecting and displaying lots of data and images and fields
         can take serious time. If your frame is updated frequently it
         could cause speed issues.

         Think about storing calculated frame content, only updating the
         necessary parts. Reduce the number of updates to the needed
         minimum. (See Caching)

         Dont make things complicated if you do not have speed issues
         but be prepared to fight them if you do.

         .. rubric:: Caching html forms
            :name: caching-html-forms

         Since building html forms can take serious amounts of time its
         a good practice to store build form html in a token property
         and reuse it as long it doesnt have to be rebuild. Its
         especially effective if you build complex stuff by accessing
         lots of property - usually the case if you build character
         sheets. When creating complex html structures and storing them
         into a token property you're asking for trouble so its common
         practice to encode them first before you store them. It's also
         best to store character sheets (token specific) onto the (n)pc
         token and general forms like weapon list, skill list, etc. onto
         a lib:token

         Here an example of 'caching' a charactersheet.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: rebuild = macro.args]

               #. .. code-block:: none

                     [h: id = currentToken()]

               #. .. code-block:: none

                     [h: output = getProperty("charSheetCache", id)]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     [h, if(rebuild || output == ""), code: {

               #. .. code-block:: none

                         [h: output = "here you build"]

               #. .. code-block:: none

                         [h: output = output + "your mega complex character sheet"]

               #. .. code-block:: none

                         ...

               #. .. code-block:: none

                         [h: output = encode(output)]

               #. .. code:: de2

                      

               #. .. code-block:: none

                         [h:'<!-- though it might be better to define a UDF for that -->']

               #. .. code-block:: none

                         [h:'<!-- e.g: output = encode(createSheetContent()) -->']

               #. .. code-block:: none

                      

               #. .. code-block:: none

                         [h: setProperty("charSheetCache", output, id)]

               #. .. code:: de2

                     };{}]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [frame("Character Sheet"):{

               #. .. code-block:: none

                         [r: decode(output)]

               #. .. code-block:: none

                     }]

         | 
         | A nice technique to individualize cached forms/html is
           described here: `Making cached structures dynamic (Load BIG
           forms
           FAST) <http://forums.rptools.net/viewtopic.php?f=20&t=16324&start=0>`__

         .. rubric:: Don't forget the token context
            :name: dont-forget-the-token-context

         When you work with macrolinks you can easily lose the token
         context. If you happen to work with explicit ids and
         get/setProperty() a lot that may be no problem for you.

         However it does change the chat output. If a macrolink is
         called with unknown token context instead of token image and
         name the chat line begins with user name.

         If you dont like this always specify the token context in your
         `macroLink() <macroLink>`__ and
         `macroLinkText() <macroLinkText>`__ calls.

         An example of this can be found in the
         `forum <http://forums.rptools.net/viewtopic.php?p=170425#p170425>`__.

         .. rubric:: Predefine checkboxes
            :name: predefine-checkboxes

         Checkboxes only create data in macro.args if they are checked.
         There is a neat trick to always create the relevant data even
         if it is unchecked. Predefine the key/value-pair using a hidden
         input with a 0 (of course you have to use the same name as your
         checkbox has). A checked checkbox will overwrite a predefined 0
         while a unchecked checkbox (as it does not generate anything)
         won't overwrite a predefined 1.

         If you want to have a initially checked checkbox you can set it
         as checked like this (regardless of beeing predefined or not)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               #. .. code-block:: none

                     <input type="checkbox" name="surprised"  value="1" checked="checked" />

         Big thanks to wolph42 for learning me this.

         .. rubric:: Don't shy away from layout tables
            :name: dont-shy-away-from-layout-tables

         In webdesign layout tables might be a no-go. Don't be afraid of
         them in maptool. They are a great way to precisly align your
         form elements. Let me demonstrate how different a simple layout
         table looks compared to a very simplistic inline approach.

         |Cif forms tutorial example layout table.png|

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("test"): {

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <h3>this is ugly</h3>

               #. .. code-block:: none

                     Value <input type="text" size="5" /><br>

               #. .. code:: de2

                     Option1<input type="checkbox" /><br>

               #. .. code-block:: none

                     Option2<input type="checkbox" /><br>

               #. .. code-block:: none

                     <input type="submit"><br>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <h3>this is pretty</h3>

               #. .. code:: de2

                     <table>

               #. .. code-block:: none

                     <tr>

               #. .. code-block:: none

                        <td>Value</td>

               #. .. code-block:: none

                        <td><input type="text" size="5" /></td>

               #. .. code-block:: none

                     </tr>

               #. .. code:: de2

                     <tr>

               #. .. code-block:: none

                        <td>Option1</td>

               #. .. code-block:: none

                        <td><input type="checkbox" /></td>

               #. .. code-block:: none

                     </tr>

               #. .. code-block:: none

                     <tr>

               #. .. code:: de2

                        <td>Option2</td>

               #. .. code-block:: none

                        </td><input type="checkbox" />

               #. .. code-block:: none

                     </td>

               #. .. code-block:: none

                     <tr>

               #. .. code-block:: none

                        <td colspan="2"><input type="submit" /></td>

               #. .. code:: de2

                     </tr>

               #. .. code-block:: none

                     </table>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     }]

         .. rubric:: The big examples
            :name: the-big-examples

         .. rubric:: Character sheet/editor
            :name: character-sheeteditor

         Lets create an character sheet and editor for the `maptool
         sample ruleset <Sample_Ruleset>`__ using what we
         learned so far.

         | 
         | |Cif forms tutorial screenshot example1.png|

         First we need a frame. We want it to auto-update with the
         selected content. We pass the selected tokens to the character
         sheet generating macro so we know what do display.

         We want more eyecandy, so we will use css. As we like
         separating css rules from the content we will place it in its
         own macro.

         **openCharacterSheet**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: link = macroLinkText("openCharacterSheet@Lib:token", "none")]

               #. .. code-block:: none

                     [frame("csheet"): {

               #. .. code-block:: none

                     <html>

               #. .. code-block:: none

                     <head>

               #. .. code:: de2

                     <link rel="onChangeSelection" type="macro" href="[r:link]">

               #. .. code-block:: none

                     <link rel="stylesheet" type="text/css" href="css@Lib:token"></link>

               #. .. code-block:: none

                     </head>

               #. .. code-block:: none

                     <body>

               #. .. code-block:: none

                     [r, macro("characterSheet@Lib:token"): getSelected()]

               #. .. code:: de2

                     </body>

               #. .. code-block:: none

                     </html>

               #. .. code-block:: none

                     }]

         **css**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: css source-css

               #. .. code-block:: none

                     .odd { background-color: #FFFFFF }

               #. .. code-block:: none

                     .even { background-color: #EEEEAA }

               #. .. code-block:: none

                     th { background-color: #113311; color: #FFFFFF }

         Then we have to actually build the character sheet. Since
         selection will cause this to be called we have to deal with
         empty and multiple selections. We'll just don't create any
         output then.

         **characterSheet**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: id = macro.args]

               #. .. code-block:: none

                     [r, if(listCount(id)!=1), code: {};{

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: link = macroLinkText("editCharacterSheet@Lib:token", "all")]

               #. .. code:: de2

                     <form action="[r:link]" method="json">

               #. .. code-block:: none

                      <input type="hidden" name="id" value="[r:id]">

               #. .. code-block:: none

                     <h1>[r:getName(id)]</h1>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <table width="*">

               #. .. code:: de2

                     <tr>

               #. .. code-block:: none

                       <th colspan="2">Primary Attributes</th>

               #. .. code-block:: none

                     </tr>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: attributes = "Strength, Dexterity, Intelligence, Endurance"]

               #. .. code:: de2

                     [h: row = "odd"]

               #. .. code-block:: none

                     [r, foreach(attrib, attributes, ""), code: {

               #. .. code-block:: none

                         <tr class="[r:row]">

               #. .. code-block:: none

                         <td><b>[r:attrib]:</b></td>

               #. .. code-block:: none

                         <td><input type="text" name="[r:attrib]" value="[r:getProperty(attrib, id)]" size="3" align="right"></td>

               #. .. code:: de2

                         </tr>

               #. .. code-block:: none

                         [h: row = if(row=="odd", "even", "odd")]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <tr>

               #. .. code:: de2

                       <th colspan="2">Secondary Attributes</th>

               #. .. code-block:: none

                     </tr>

               #. .. code-block:: none

                     [h: attributes = "Hit Points, Armor, Movement"]

               #. .. code-block:: none

                     [h: row = "odd"]

               #. .. code-block:: none

                     [r, foreach(attrib, attributes, ""), code: {

               #. .. code:: de2

                         <tr class="[r:row]">

               #. .. code-block:: none

                         <td><b>[r:attrib]:</b></td>

               #. .. code-block:: none

                         <td>[r:getProperty(attrib, id)]</td>

               #. .. code-block:: none

                         </tr>

               #. .. code-block:: none

                         [h: row = if(row=="odd", "even", "odd")]

               #. .. code:: de2

                     }]

               #. .. code-block:: none

                     [h: classes = "Warrior, Rogue, Wizard, Priest"]

               #. .. code-block:: none

                     [h: CharClass = getProperty("CharClass", id)]

               #. .. code-block:: none

                     <tr class="[r:row]">

               #. .. code-block:: none

                         <td><b>Class:</b></td>

               #. .. code:: de2

                         <td>

               #. .. code-block:: none

                             <select name="CharClass" size="1">

               #. .. code-block:: none

                             [r, foreach(c, classes, ""), code: {

               #. .. code-block:: none

                                 <option [r, if(c==CharClass): "selected"]>[r:c]</option>

               #. .. code-block:: none

                             }]

               #. .. code:: de2

                         </select>

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                     </tr>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <input type="submit" name="edit_btn" value="Submit changes">

               #. .. code:: de2

                     </form>

               #. .. code-block:: none

                     }]

         If the submit button is pressed we want to save the changes
         back to the token.

         **editCharacterSheet**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: arguments = macro.args] 

               #. .. code-block:: none

                     [h: id = json.get(arguments, "id")]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <!-- set primary attributes -->

               #. .. code:: de2

                     [h: attributes = "Strength, Dexterity, Intelligence, Endurance"]

               #. .. code-block:: none

                     [h, foreach(attrib, attributes), code: {

               #. .. code-block:: none

                         [h: val = json.get(macro.args, attrib)]

               #. .. code-block:: none

                         [h, if(! isNumber(val)): val=eval(val)]

               #. .. code-block:: none

                         <!-- allowed values are 1..6 -->

               #. .. code:: de2

                         [h: val = min(max(val,1), 6)]

               #. .. code-block:: none

                         [r: setProperty(attrib, val, id)]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: setProperty("Hit Points", 6*getProperty("Endurance",id), id)]

               #. .. code:: de2

                     [h: setProperty("Class", json.get(macro.args, "CharClass"), id)]

               #. .. code-block:: none

                     [h: setProperty("Movement", getProperty("Dexterity",id), id)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: CharClass = getProperty("CharClass", id)]

               #. .. code:: de2

                      

               #. .. code-block:: none

                      

               #. .. code-block:: none

                      

               #. .. code-block:: none

                      

               #. .. code-block:: none

                      

               #. .. code:: de2

                     [h, switch(CharClass):

               #. .. code-block:: none

                         case "Warrior": val=6;

               #. .. code-block:: none

                         case "Rogue": val=2;

               #. .. code-block:: none

                         case "Wizard": val=1;

               #. .. code-block:: none

                         case "Priest": val=4;

               #. .. code:: de2

                        default: val=0

               #. .. code-block:: none

                     ]

               #. .. code-block:: none

                     [h: setProperty("Armor", val, id)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: setProperty("Hit Points", 6*getProperty("Endurance",id), id)]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     Changes saved to [r: getName(id)].

               #. .. code-block:: none

                     [h, macro("openCharacterSheet@Lib:token"): id]

         If you'd want to play with this you'd surely come up with lots
         of improvements .. great! I would as well. But this should be
         enough to demonstrate building a character sheet or editor with
         html forms.

         **Download** this
         example:\ `example1.rptok <http://www.bastian-dornauf.de/example1.rptok>`__\ (token
         is saved with b73) Drop this libtoken into an empty map and toy
         around with it.

         .. rubric:: Click-based Target selection
            :name: click-based-target-selection

         There are very differen ways how to select targets of an
         action. The clickbased targeting (first done by Rumble) works
         best in maptool version b70 or later with the "unowned
         selection" feature.

         | 
         | |Cif forms tutorial screenshot example2.png|

         You impersonate or select the active token. Then you execute a
         macro, eg "Attack" that opens a frame. In that frame you can
         enter additional infos like modifier. While that frame is open
         you select ((with the mouse on the map)) the target(s) of the
         attack. The frame has a button that actually performs the
         attack.

         Lets start with the macro that opens that frame.

         **openActionFrame**

         This macro first determines what token should be considered the
         *active* token. A token impersonated would be preferred.
         Otherwise the selection is taken. If no or multiple tokens are
         selected the macro us aborted.

         Then the macro checks if the user has the right to perform
         actions with that token - he has if he is GM or own the token.

         After that the current selection is cleared and the frame
         displaying code is called.

         If you have different actions to perform here would the place
         to branch into different actionFrames according to the chosen
         action.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: chosenAction = macro.args]

               #. .. code-block:: none

                     [h, if(hasImpersonated()): activeId = getImpersonated(); activeId = getSelected()]

               #. .. code-block:: none

                     [h, if(listCount(activeId)!=1): assert(0, "You have to select only one token")]

               #. .. code-block:: none

                     [h: gm = isGM()]

               #. .. code:: de2

                     [h: owned = isOwner(getPlayerName(), activeId)]

               #. .. code-block:: none

                     [h, if(gm ||  owned): ""; assert(0, "You have no right to act with this token.")]

               #. .. code-block:: none

                     [h: deselectTokens()]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <!-- call right actionFrame for chosenAction -->

               #. .. code:: de2

                     [r, macro("actionFrame@Lib:tkn"): activeId]

         | 
         | Now we need a way for the user to call this macro. This can
           be either a campaign or a token macro - depending on your
           taste.

         **Attack**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r, macro("openActionFrame@Lib:token"):"Attack"]

         *Note* that I send ``"Attack"`` to the frame opening macro and
         that this is placed in a variable named ``chosenAction``. It is
         never used. If you want to support different actions (like
         ranged and melee attacks) you could, right after the comment,
         branch - depending on ``chosenAction`` - into different
         actionFrame.

         **actionFrame** This is pretty simple. It shows a frame and
         uses the ``onChangeSelection``-event to display the targets.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: activeId = macro.args]

               #. .. code-block:: none

                     [h: selection = getSelected()]

               #. .. code-block:: none

                     [h: link = macroLinkText("actionFrame@Lib:tkn", "none", activeId)]

               #. .. code-block:: none

                     [h: perform= macroLinkText("performAction@Lib:tkn", "all")]

               #. .. code:: de2

                     [frame("Action"): {

               #. .. code-block:: none

                     <html>

               #. .. code-block:: none

                     <head>

               #. .. code-block:: none

                     <link rel='onChangeSelection' type='macro' href='[r:link]'>

               #. .. code-block:: none

                     </head>

               #. .. code:: de2

                     <body>

               #. .. code-block:: none

                     <b>Attacker:</b><br>

               #. .. code-block:: none

                     [r, token(activeId): strformat("<img src='%s' alt='%s'>", getTokenImage(50), getName())]

               #. .. code-block:: none

                     <br>

               #. .. code-block:: none

                     <b>Targets:</b> <br>

               #. .. code:: de2

                     [r, foreach(id, selection, " "), code: {

               #. .. code-block:: none

                     [r, token(id): strformat("<img src='%s' alt='%s'>", getTokenImage(50), getName())]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                     <form action="[r:perform]" method="json">

               #. .. code-block:: none

                     <input type="text" name="mods" value="0"><br>

               #. .. code:: de2

                     <input type="submit" name="btn_submit" value="Perform action">

               #. .. code-block:: none

                     <input type="hidden" name="id" value="[r:activeId]">

               #. .. code-block:: none

                     <input type="hidden" name="targets" value="[r:selection]">

               #. .. code-block:: none

                     }]

         **performAction**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: arguments = macro.args]

               #. .. code-block:: none

                     [h: id = json.get(arguments, "id")]

               #. .. code-block:: none

                     [h: targets = json.get(arguments, "targets")]

               #. .. code-block:: none

                     [h, if(listCount(targets)<1): abort(0)]

               #. .. code:: de2

                     <!-- target and performer could be the same -->

               #. .. code-block:: none

                     <!-- target could be one or many -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <!-- roll the attack -->

               #. .. code-block:: none

                     <b>Melee attack:</b><br>

               #. .. code:: de2

                     [r, foreach(target, targets, "<br>"), code: {

               #. .. code-block:: none

                         <b>[r: getName(id)]</b> rolls

               #. .. code-block:: none

                         [r, token(id): rollResult = 1d20 + Strength]

               #. .. code-block:: none

                         [r, if(rollResult>=15), code: {

               #. .. code-block:: none

                             and hits <b>[r:getName(target)]</b> for

               #. .. code:: de2

                             [r: dmg = 1d6 + getProperty("Strength", id) - getProperty("Armor", target)]

               #. .. code-block:: none

                             points of damage.

               #. .. code-block:: none

                             [h: setProperty("Hit Points", getProperty("Hit Points", target) - max(0,dmg), target)]

               #. .. code-block:: none

                         };{and misses [r:getName(target)]}]

               #. .. code-block:: none

                     }]

         This macro does the actual attack. The attacker and the targets
         are submitted via ``macro.args``. The rest is the usual dice
         rolling and comparing to target numbers and stuff...

         Again this could be done better. It doesnt modify the roll by
         the entered mods. It does not even model the sample ruleset
         right. You'd want to support attack powers and maybe set states
         for being wounded or dead.

         But it demonstrates how to target .. the rest is up to you.

         **Download** a lib token for this example
         `example2.rptok <http://www.bastian-dornauf.de/example2.rptok>`__
         (token is saved with b73)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Forms_tutorial&oldid=6299"

