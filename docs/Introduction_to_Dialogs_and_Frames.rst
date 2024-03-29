===============================================
Introduction to Dialogs and Frames - MapToolDoc
===============================================

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

   .. rubric:: Introduction to Dialogs and Frames
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

         .. container:: template_advanced

            ADVANCED
            THIS IS AN ADVANCED ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 An Introduction to MapTool Macro Dialogs and
               Frames <#An_Introduction_to_MapTool_Macro_Dialogs_and_Frames>`__

               -  `1.1 First Steps <#First_Steps>`__
               -  `1.2 Adding Some HTML <#Adding_Some_HTML>`__
               -  `1.3 Now for a dash of CSS <#Now_for_a_dash_of_CSS>`__
               -  `1.4 And a Touch more
                  formatting <#And_a_Touch_more_formatting>`__
               -  `1.5 Creating Support
                  Functions <#Creating_Support_Functions>`__
               -  `1.6 Input Dialogs <#Input_Dialogs>`__
               -  `1.7 Creating a Simple Character Sheet
                  Frame <#Creating_a_Simple_Character_Sheet_Frame>`__
               -  `1.8 Related Pages <#Related_Pages>`__

         .. rubric:: An Introduction to MapTool Macro Dialogs and Frames
            :name: an-introduction-to-maptool-macro-dialogs-and-frames

         Please note I will be using CSS and HTML in this tutorial but I
         will not really be explaining them, if you need a refresher on
         either a search on
         `google <http://www.google.com.au/search?q=HTML+and+CSS+Tutorials>`__
         will point you to many resources that do a better job than I
         could.

         | 
         | The `[dialog():] <dialog_(roll_option)>`__ and
           `[frame():] <frame_(roll_option)>`__ `roll
           types <Macros:Roll:types>`__ create a new
           dialog or frame where all the output from the commands within
           the {} will be displayed. dialog create a dialog box that
           hovers over other windows. frame creates a frame that can be
           docked like the other maptool windows. The dialog and frame
           windows can be used to display HTML and rolls the same as the
           chat output window.

         This tutorial starts with the standard blank campaign you get
         when you start MapTool, anything else we need we will add along
         the way.

         .. rubric:: First Steps
            :name: first-steps

         So lets jump in and create your first dialog, you can use the
         code below to create a dialog.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                       Your first dialog!

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image0|

                  .. container:: thumbcaption

                     Example Dialog

         I know its pretty boring but before we start adding more to it
         lets create a frame so that you can see the difference

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("Test"): {

               #. .. code-block:: none

                       Your first frame!

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image1|

                  .. container:: thumbcaption

                     Example Frame

         | 
         | And a picture of your first frame docked.

         | 

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image2|

                  .. container:: thumbcaption

                     Example Docked Frame

         Back to the dialog you can spice it up a little with some `dice
         rolls <Macros:Roll:types>`__ and HTML formatting.

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                       <b>1d4</b> -> [1d4]<br>

               #. .. code-block:: none

                       <b>1d6</b> -> [1d6]<br>

               #. .. code-block:: none

                       <b>1d8</b> -> [1d8]<br>

               #. .. code:: de2

                       <b>1d10</b> -> [1d10]<br>

               #. .. code-block:: none

                       <b>1d12</b> -> [1d12]<br>

               #. .. code-block:: none

                       <b>1d20</b> -> [1d20]<br>

               #. .. code-block:: none

                       <b>1d100</b> -> [1d100]<br>

               #. .. code-block:: none

                     }]

         | 

         .. rubric:: Adding Some HTML
            :name: adding-some-html

         This will create a dialog box with some HTML formatting and
         `dice rolls <Macros:Roll:types>`__. The `dice
         rolls <Macros:Roll:types>`__ will have all the
         tooltips that you would normally get in the chat output.

         Still the title is boring (it defaults to the name of the
         dialog). You can use the HTML <title> tag to change the title.
         Run the code below, there is no need to close the dialog from
         the code above.

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code-block:: none

                           <title>Dice Roll Dialog</title>

               #. .. code:: de2

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <b>1d4</b> -> [1d4]<br>

               #. .. code-block:: none

                           <b>1d6</b> -> [1d6]<br>

               #. .. code-block:: none

                           <b>1d8</b> -> [1d8]<br>

               #. .. code:: de2

                           <b>1d10</b> -> [1d10]<br>

               #. .. code-block:: none

                           <b>1d12</b> -> [1d12]<br>

               #. .. code-block:: none

                           <b>1d20</b> -> [1d20]<br>

               #. .. code-block:: none

                           <b>1d100</b> -> [1d100]<br>

               #. .. code-block:: none

                         </body>

               #. .. code:: de2

                       </html>

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image3|

                  .. container:: thumbcaption

                     Example Dice Roll Dialog

         Notice that the dialog command did not open a new dialog
         window, instead it replaced the contents of the dialog you had
         open. When you use [dialog()] with the name of a dialog that
         already exists the contents of that dialog are replaced,
         (`[frame()] <frame_(roll_option)>`__ works the
         same way). You can use this behavior to update your dialogs.
         Create a token called
         `Lib:Test <Library_Token>`__ with a macro
         (created on that lib:Test token) called Test

         Copy the following code into the Test macro.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code-block:: none

                           <title>Dice Roll Dialog</title>

               #. .. code:: de2

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <b>1d4</b> -> [1d4]<br>

               #. .. code-block:: none

                           <b>1d6</b> -> [1d6]<br>

               #. .. code-block:: none

                           <b>1d8</b> -> [1d8]<br>

               #. .. code:: de2

                           <b>1d10</b> -> [1d10]<br>

               #. .. code-block:: none

                           <b>1d12</b> -> [1d12]<br>

               #. .. code-block:: none

                           <b>1d20</b> -> [1d20]<br>

               #. .. code-block:: none

                           <b>1d100</b> -> [1d100]<br>

               #. .. code-block:: none

                           <br>

               #. .. code:: de2

                           [macroLink("Refresh", "Test@Lib:Test")]

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image4|

                  .. container:: thumbcaption

                     Example Dice Roll Dialog with Refresh macroLink

         | 
         | The above macro uses the
           `macroLink() <Macros:Functions:macroLink>`__
           function to create a link that will call Test on
           `Lib:Test <Library_Token>`__ when ever it is
           clicked (which will update the dialog with new rolls).

         The above would be really useful if you needed a window that
         provided you with a bunch of dice rolls all the time. But I
         assume that is not what most people will want to do with the
         dialogs.

         Drag another `token <Token>`__ out on to the map,
         and fill in the `token
         properties <Token:token_property>`__. We can
         create a simple character sheet with a dialog. On the
         `Lib:Test <Library_Token>`__ token create a macro
         called CharSheet and paste the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]

               #. .. code-block:: none

                     [dialog("CharSheetTest"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code:: de2

                           <title>Character Sheet</title>

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <table>

               #. .. code-block:: none

                             [foreach(prop, propNames, ""), code: {

               #. .. code:: de2

                               <tr>

               #. .. code-block:: none

                                 <td>[r: prop]</td>

               #. .. code-block:: none

                                 <td>[r: getProperty(prop)]</td>

               #. .. code-block:: none

                               </tr>

               #. .. code-block:: none

                             }]

               #. .. code:: de2

                           </table>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code-block:: none

                     }]

         On the new `Token <Token>`__ that you placed on
         the map create a `macro button <Macro_Button>`__
         called CharSheet and paste the following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("CharSheet@Lib:Test"): ""]

               #. .. code-block:: none

                     [abort(0)]

         Click on the new `macro button <Macro_Button>`__.

         .. rubric:: Now for a dash of CSS
            :name: now-for-a-dash-of-css

         Again we are not going to set the world on fire with this
         character sheet dialog. Lets spice it up a little, I will show
         you how to use some CSS for formatting.

         To use CSS you insert a link like the following into the HTML
         to be displayed.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                         <link rel='stylesheet' type='text/css' href='myCSS@Lib:Test'></link>

               #. .. code-block:: none

                     }]

         | 
         | Although you can (and probably should) use the
           `getMacroLocation() <Macros:Functions:getMacroLocation>`__
           function to make sure it comes from the same
           `Lib:Token <Library_Token>`__ as the macro. So,

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Test"): {

               #. .. code-block:: none

                         <link rel='stylesheet' type='text/css' href='myCSS@[r: getMacroLocation()]'></link>

               #. .. code-block:: none

                     }]

         Edit the CharSheet macro on the
         `Lib:Test <Library_Token>`__
         `Token <Token>`__ and paste in the following.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]

               #. .. code-block:: none

                     [dialog("CharSheetTest"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code:: de2

                           <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                           <title>Character Sheet</title>

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <table id="stats">

               #. .. code:: de2

                             <tr>

               #. .. code-block:: none

                               <th>Name</th>

               #. .. code-block:: none

                               <th>Score</th>

               #. .. code-block:: none

                             </tr>

               #. .. code-block:: none

                             [h: class = "oddRow"]

               #. .. code:: de2

                             [foreach(prop, propNames, ""), code: {

               #. .. code-block:: none

                               <tr class="[r:class]">

               #. .. code-block:: none

                                 <td>[r: prop]</td>

               #. .. code-block:: none

                                 <td>[r: getProperty(prop)]</td>

               #. .. code-block:: none

                               </tr>

               #. .. code:: de2

                               [h: class = if(class=="oddRow", "evenRow", "oddRow")]

               #. .. code-block:: none

                             }]

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code:: de2

                     }]

         Also create a new `macro button <Macro_Button>`__
         on `Lib:Test <Library_Token>`__ called
         CharSheet_css and paste the following CSS code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     .oddRow { background-color: #FFFFFF }

               #. .. code-block:: none

                     .evenRow { background-color: #EEEEAA }

               #. .. code-block:: none

                     #stats th { background-color: #113311; color: #FFFFFF }

         Click on the CharSheet `macro
         button <Macro_Button>`__ on your
         `Token <Token>`__.

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image5|

                  .. container:: thumbcaption

                     Simple Character Sheet with a Style Sheet

         Looks much better already!

         Getting better... Lets make some more changes. Change the
         CharSheet macro on `Lib:Test <Library_Token>`__
         to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]

               #. .. code-block:: none

                     [dialog("CharSheetTest"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code:: de2

                           <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                           <title>Character Sheet</title>

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <table>

               #. .. code:: de2

                             <tr>

               #. .. code-block:: none

                               <td>

               #. .. code-block:: none

                                 <img src='[r: getTokenImage(100)]'></img>

               #. .. code-block:: none

                               </td>

               #. .. code-block:: none

                               <td>

               #. .. code:: de2

                                 <table id="stats">

               #. .. code-block:: none

                                   <tr>

               #. .. code-block:: none

                                     <th>Name</th>

               #. .. code-block:: none

                                     <th>Score</th>

               #. .. code-block:: none

                                   </tr>

               #. .. code:: de2

                                   [h: class = "oddRow"]

               #. .. code-block:: none

                                   [foreach(prop, propNames, ""), code: {

               #. .. code-block:: none

                                     <tr class="[r:class]">

               #. .. code-block:: none

                                       <td>[r: prop]</td>

               #. .. code-block:: none

                                       <td>[r: getProperty(prop)]</td>

               #. .. code:: de2

                                     </tr>

               #. .. code-block:: none

                                     [h: class = if(class=="oddRow", "evenRow", "oddRow")]

               #. .. code-block:: none

                                   }]

               #. .. code-block:: none

                                 </table>

               #. .. code-block:: none

                               </td>

               #. .. code:: de2

                             </tr>

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                           <hr>

               #. .. code-block:: none

                           <table>

               #. .. code-block:: none

                             <tr>

               #. .. code:: de2

                               <th>Hit Points:</th>

               #. .. code-block:: none

                               <td>[r: HP]</td>

               #. .. code-block:: none

                               <th>Armor Class:</th>

               #. .. code-block:: none

                               <td>[r: AC]</td>

               #. .. code-block:: none

                             </tr>

               #. .. code:: de2

                           </table>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image6|

                  .. container:: thumbcaption

                     Simple Character Sheet with Token Image

         Looks much better already!

         .. rubric:: And a Touch more formatting
            :name: and-a-touch-more-formatting

         Ok in Edit->Campaign Properties, Token Properties Tab, Basic
         Token type, add the following properties

         -  \*@MaxHP
         -  \*@XP
         -  \*@NextLevelXP

         | 
         | Then edit your `Token <Token>`__ and set some
           values in your new
           `properties <Token_Property>`__.

         Time to create a new `macro
         button <Macro_Button>`__ on the
         `Lib:Test <Library_Token>`__ called
         TrafficLightBar and paste the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- ======================================================================

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ==== Outputs a red/yellow/green bar

               #. .. code-block:: none

                          ====

               #. .. code:: de2

                          ==== Parameters (accepts a string property list with following keys)

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ====   MaxLen - Maximum length of status bar.

               #. .. code-block:: none

                          ====   MaxValue - The "Full" value for the bar.

               #. .. code-block:: none

                          ====   Value - The current value for the bar.

               #. .. code:: de2

                          ====   Label - The label for the bar.

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ====================================================================== -->

               #. .. code-block:: none

                     <!-- Set up the colors for our "Traffic Lights" -->

               #. .. code-block:: none

                     [h: r0=200] [h: g0=200] [h: b0=200]

               #. .. code:: de2

                     [h: r1=200] [h: g1=0]   [h: b1=0]

               #. .. code-block:: none

                     [h: r2=255] [h: g2=140] [h: b2=0]

               #. .. code-block:: none

                     [h: r3=0]   [h: g3=200] [h: b3=0]

               #. .. code-block:: none

                     [h: MaxLen=getStrProp(macro.args, "MaxLen")]

               #. .. code-block:: none

                     [h: MaxValue=getStrProp(macro.args, "MaxValue")]

               #. .. code:: de2

                     [h: Value=getStrProp(macro.args, "Value")]

               #. .. code-block:: none

                     [h: Label=getStrProp(macro.args, "Label")]

               #. .. code-block:: none

                     [h: Len=max(min(round(Value*MaxLen/MaxValue+0.4999),MaxLen),0)]

               #. .. code-block:: none

                     [h: Len=if(Value>=MaxValue,MaxLen, Len)]

               #. .. code-block:: none

                     [h: c=min(round(Value*3/MaxValue+0.4999),3)]

               #. .. code:: de2

                     [h: col=min(max(Len,0),1)*c]

               #. .. code-block:: none

                     [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       <tr>

               #. .. code-block:: none

                         <td><span title="{Value}/{MaxValue}">{Label}</span></td>

               #. .. code:: de2

                         <td style="background-color: rgb({r},{g},{b})">

               #. .. code-block:: none

                           <span title="{Value}/{MaxValue}">[c(Len, ""),r: "&nbsp;"]</span>

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                         [if(MaxLen-Len>0), code: {

               #. .. code-block:: none

                           <td style="background-color: rgb({r0},{g0},{b0})">

               #. .. code:: de2

                             <span title="{Value}/{MaxValue}">[c(MaxLen-Len,""),r: "&nbsp;"]</span>

               #. .. code-block:: none

                           </td>

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                       </tr>

               #. .. code-block:: none

                     </table>

         Create another `macro button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ called StatusBar and
         copy the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- ======================================================================

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ==== Outputs a "progress" bar

               #. .. code-block:: none

                          ====

               #. .. code:: de2

                          ==== Parameters (accepts a string property list with following keys)

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ====   MaxLen - Maximum length of status bar.

               #. .. code-block:: none

                          ====   MaxValue - The "Full" value for the bar.

               #. .. code-block:: none

                          ====   Value - The current value for the bar.

               #. .. code:: de2

                          ====   Label - The label for the bar.

               #. .. code-block:: none

                          ====   Color - R,G,B color

               #. .. code-block:: none

                          ====

               #. .. code-block:: none

                          ====================================================================== -->

               #. .. code-block:: none

                     [h: r0=200] [h: g0=200] [h: b0=200]

               #. .. code:: de2

                     [h: MaxLen=getStrProp(macro.args, "MaxLen")]

               #. .. code-block:: none

                     [h: MaxValue=getStrProp(macro.args, "MaxValue")]

               #. .. code-block:: none

                     [h: Value=getStrProp(macro.args, "Value")]

               #. .. code-block:: none

                     [h: Color=getStrProp(macro.args, "Color")]

               #. .. code-block:: none

                     [h: Label=getStrProp(macro.args, "Label")]

               #. .. code:: de2

                     [h: r1=listGet(Color,0)]

               #. .. code-block:: none

                     [h: g1=listGet(Color,1)]

               #. .. code-block:: none

                     [h: b1=listGet(Color,2)]

               #. .. code-block:: none

                     [h: Len=max(min(round(Value*MaxLen/MaxValue+0.4999),MaxLen),0)]

               #. .. code-block:: none

                     [h: c=min(round(Value/MaxValue+0.4999),1)]

               #. .. code:: de2

                     [h: col=min(max(Len,0),1)*c]

               #. .. code-block:: none

                     [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]

               #. .. code-block:: none

                     [h: r=eval("r"+col)] [h: g=eval("g"+col)] [h: b=eval("b"+col)]

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       <tr>

               #. .. code:: de2

                         <td><span title="{Value}/{MaxValue}">{Label}</span></td>

               #. .. code-block:: none

                         <td style="background-color: rgb({r},{g},{b})">

               #. .. code-block:: none

                           <span title="{Value}/{MaxValue}">[c(Len, ""),r: "&nbsp;"]</span>

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                         [if(MaxLen-Len>0), code: {

               #. .. code:: de2

                           <td style="background-color: rgb({r0},{g0},{b0})">

               #. .. code-block:: none

                             <span title="{Value}/{MaxValue}">[c(MaxLen-Len,""),r: "&nbsp;"]</span>

               #. .. code-block:: none

                           </td>

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                       </tr>

               #. .. code:: de2

                     </table>

         I am really going to gloss over the previous two functions a
         bit as they are not important to understanding how to use
         dialogs or frames, but so you know what they do TrafficLightBar
         creates a red/yellow/green bar where the color is based on how
         full the bar is. StatusBar just creates a bar that is one
         color.

         Just a quick point for those who may not know this already, but
         when you call a macro with `[macro("name"):
         arguments] <macro_(roll_option)>`__ the arguments
         are available in the macro in the variable
         `macro.args <macro.args>`__. To return a value
         from the macro you read the variable
         `macro.return <macro.return>`__, the calling
         macro can then read
         `macro.return <macro.return>`__ to get this
         value.

         Then we change the CharSheet macro on
         `Lib:Test <Library_Token>`__ to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]

               #. .. code-block:: none

                     [dialog("CharSheetTest"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code:: de2

                           <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                           <title>Character Sheet</title>

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <table>

               #. .. code:: de2

                             <tr>

               #. .. code-block:: none

                               <td>

               #. .. code-block:: none

                                 <img src='[r: getTokenImage(100)]'></img>

               #. .. code-block:: none

                               </td>

               #. .. code-block:: none

                               <td>

               #. .. code:: de2

                                 <table id="stats">

               #. .. code-block:: none

                                   <tr>

               #. .. code-block:: none

                                     <th>Name</th>

               #. .. code-block:: none

                                     <th>Score</th>

               #. .. code-block:: none

                                   </tr>

               #. .. code:: de2

                                   [h: class = "oddRow"]

               #. .. code-block:: none

                                   [foreach(prop, propNames, ""), code: {

               #. .. code-block:: none

                                     <tr class="[r:class]">

               #. .. code-block:: none

                                       <td>[r: prop]</td>

               #. .. code-block:: none

                                       <td>[r: getProperty(prop)]</td>

               #. .. code:: de2

                                     </tr>

               #. .. code-block:: none

                                     [h: class = if(class=="oddRow", "evenRow", "oddRow")]

               #. .. code-block:: none

                                   }]

               #. .. code-block:: none

                                 </table>

               #. .. code-block:: none

                               </td>

               #. .. code:: de2

                             </tr>

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                           <hr>

               #. .. code-block:: none

                           <table>

               #. .. code-block:: none

                             <tr>

               #. .. code:: de2

                               <td>

               #. .. code-block:: none

                                 [h: hpBarArgs = strformat("MaxLen=50; Value=%{HP}; MaxValue=%{MaxHP}; Label=HP")]

               #. .. code-block:: none

                                 [macro("TrafficLightBar@this"): hpBarArgs]

               #. .. code-block:: none

                               </td>

               #. .. code-block:: none

                             </tr>

               #. .. code:: de2

                             <tr>

               #. .. code-block:: none

                               <td>

               #. .. code-block:: none

                                 [h: hpBarArgs = strformat("MaxLen=50; Value=%{XP}; MaxValue=%{NextLevelXP}; Label=XP; Color=120,120,255")]

               #. .. code-block:: none

                                 [macro("StatusBar@this"): hpBarArgs]

               #. .. code-block:: none

                               </td>

               #. .. code:: de2

                             </tr>

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code-block:: none

                     }]

         | 
         | Click on the CharSheet `macro
           button <Macro_Button>`__ on your
           `Token <Token>`__ again and you will have a new
           character sheet.

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image7|

                  .. container:: thumbcaption

                     Simple Character Sheet with Progress Bars

         | 
         | The above example uses
           `strformat() <Macros:Functions:strformat>`__
           which allows you to insert variables in a string using
           the %{*var*} syntax. It also has other flags that can be used
           to format variable output

         .. rubric:: Creating Support Functions
            :name: creating-support-functions

         Lets leave the character sheet at this for the moment and move
         on to a new example.

         Edit->Campaign Properties, Token Properties Tab, Basic Token
         type, add the following properties

         -  Weapons
         -  Items

         | 
         | We are going to store our weapons in a `string property
           list <String_Property_List>`__ with the
           following keys.

         -  NumWeapons - The number of weapons in our property list.
         -  UsingWeapon - The weapon we are currently using.
         -  WeaponXName - The name of weapon number X
         -  WeaponXDamage - The damage of weapon number X
         -  WeaponXBonus - The bonus of weapon number X

         We could add a lot more, but lest keep it semi simple for this
         post.

         The first thing we need is a way to enter weapons, we could use
         the `input() <input>`__ function but since this
         is a tutorial on frames and dialogs, I should probably show you
         how to do it in a dialog.

         But first we need to do some set up, when the player creates a
         new weapon we will need to get NumWeapons add 1 to it, save it
         back to the property and use that number (lets not worry about
         what happens if a player cancels the entry of the weapon as we
         are not really that worried if we have gaps in our numbering
         scheme). One problem is though what do we do first time around
         since the `string property
         list <String_Property_List>`__ would be empty so
         trying to use the `token
         property <Token_Property>`__ Weapons in
         strProp*() functions would result in the user being prompted
         for a value. We could add a default value in the campaign for
         the token, but there are also other methods. One thing we can
         do is use the
         `isPropertyEmpty() <isPropertyEmpty>`__ function
         to check if the `property <Token_Property>`__ is
         empty and if so use a initial value for it, or the
         `getProperty() <getProperty>`__ function that
         will just return an empty string ("") not prompt if there is no
         `property <Token_Property>`__.

         So lets create a macro that returns the number of a new weapon.
         Create a `macro button <Macro_Button>`__ called
         NextWeaponNumber and then paste the following code into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!--

               #. .. code-block:: none

                       Returns the number for the next weapon as well as updating the

               #. .. code-block:: none

                       the counter.

               #. .. code-block:: none

                       -->

               #. .. code:: de2

                      

               #. .. code-block:: none

                     <!-- If Weapons token property is empty set it to a default value -->

               #. .. code-block:: none

                     [h,if(isPropertyEmpty("Weapons")): Weapons = "NumWeapons=0;"]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: numWeapons = getStrProp(Weapons, "NumWeapons") + 1]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     <!-- Now update our property -->

               #. .. code-block:: none

                     [h: Weapons = setStrProp(Weapons, "NumWeapons", numWeapons)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     <!-- Finally set out return value -->

               #. .. code:: de2

                     [h: macro.return = numWeapons]

         | 
         | You can test it by running the following code from chat a few
           times

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("NextWeaponNumber@Lib:Test"): ""] [macro.return]

         | 
         | When you are done you can reset the weapon count simply by
           editing the `token
           properties <Token_Property>`__ and clearing out
           the text for weapons.

         Lets also make a `macro button <Macro_Button>`__
         called AddWeapon which takes a `string property
         list <Macros:string_property_list>`__ with the
         following keys

         -  Name
         -  Damage
         -  Bonus
         -  Number

         And adds or updates the weapon in the `string property
         list <Macros:string_property_list>`__.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!--

               #. .. code-block:: none

                       Adds a weapon to the Weapons property list

               #. .. code-block:: none

                      

               #. .. code-block:: none

                       Parameters (in a string property list)

               #. .. code:: de2

                      

               #. .. code-block:: none

                       Name = Name of Weapon

               #. .. code-block:: none

                       Damage = Damage Weapon does

               #. .. code-block:: none

                       Bonus = Bonus of Weapon

               #. .. code-block:: none

                       Number = The index number of the Weapon

               #. .. code:: de2

                     -->

               #. .. code-block:: none

                     [h: num = getStrProp(macro.args, "Number")]

               #. .. code-block:: none

                     [h: damage = getStrProp(macro.args, "Damage")]

               #. .. code-block:: none

                     [h: name = getStrProp(macro.args, "Name")]

               #. .. code-block:: none

                     [h: bonus = getStrProp(macro.args, "Bonus")]

               #. .. code:: de2

                     [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Name"), name)]

               #. .. code-block:: none

                     [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Damage"), damage)]

               #. .. code-block:: none

                     [h: Weapons = setStrProp(Weapons, strformat("Weapon%{num}Bonus"), bonus)]

         You can test this macro too by a little typing at the command
         line.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("AddWeapon@Lib:Test"): "Number=1; Damage=1d8; Name=LongSword; Bonus=0"]

         Look at the Weapons [Token_Property|property]] and see how its
         built up our `string property
         list <Macros:string_property_list>`__ for us. It
         wont have modified NumWeapons but that is ok we are going to
         assume that NextWeaponNumber is always used before adding a new
         weapon. Before clearing out the Weapons
         `property <Token_Property>`__ to reset it lets
         write a function to retrieve a weapon.

         Create a `macro button <Macro_Button>`__ called
         GetWeapon on your `Lib:Test <Library_Token>`__
         `Token <Token>`__ and paste the following into
         it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!--

               #. .. code-block:: none

                       Retrieves a weapon from the Weapons Property list.

               #. .. code-block:: none

                      

               #. .. code-block:: none

                       Parameters

               #. .. code:: de2

                         Weapon Number

               #. .. code-block:: none

                      

               #. .. code-block:: none

                       Returns

               #. .. code-block:: none

                         A string property list with following keys

               #. .. code-block:: none

                           Name = Name of Weapon

               #. .. code:: de2

                           Damage = Damage Weapon does

               #. .. code-block:: none

                           Bonus = Bonus of Weapon

               #. .. code-block:: none

                           Number = The index number of the Weapon

               #. .. code-block:: none

                         If the weapon is not found then an empty string ("") is returned.

               #. .. code-block:: none

                     -->

               #. .. code:: de2

                     [h: num = macro.args]

               #. .. code-block:: none

                     [h: damage = getStrProp(Weapons, strformat("Weapon%{num}Damage"))]

               #. .. code-block:: none

                     [h: name = getStrProp(Weapons, strformat("Weapon%{num}Name"))]

               #. .. code-block:: none

                     [h: bonus = getStrProp(Weapons, strformat("Weapon%{num}Bonus"))]

               #. .. code-block:: none

                     [h, if(name == ""):

               #. .. code:: de2

                        macro.return = ""

               #. .. code-block:: none

                     ;

               #. .. code-block:: none

                        macro.return = strformat("Number=%{num}; Damage=%{damage}; Bonus=%{bonus}; Name=%{name}")

               #. .. code-block:: none

                     ]

         | 
         | Test it with

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h, macro("GetWeapon@Lib:Test"): 1] [macro.return]

         Lets add a way to delete items. Create a `macro
         button <Macro_Button>`__ called DeleteWeapon and
         paste the following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- ============================================================ -->

               #. .. code-block:: none

                     <!-- ============================================================ -->

               #. .. code-block:: none

                     <!-- ============================================================ -->

               #. .. code-block:: none

                     <!--

               #. .. code:: de2

                       Deletes a weapon from the Weapons property List.

               #. .. code-block:: none

                      

               #. .. code-block:: none

                       Parameters

               #. .. code-block:: none

                         The weapon number

               #. .. code-block:: none

                     -->

               #. .. code:: de2

                     [h: num = macro.args]

               #. .. code-block:: none

                     [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Damage"))]

               #. .. code-block:: none

                     [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Name"))]

               #. .. code-block:: none

                     [h: Weapons = deleteStrProp(Weapons, strformat("Weapon%{num}Bonus"))]

         One more "setup" function then we should be good to go. Lets
         create a function that returns a `string
         list <Macros:string_list>`__ of all the item
         numbers (remember we can have gaps because a user could cancel
         the addition of the item after calling NextWeaponNumber or they
         could delete a weapon). Create a `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ called
         GetWeaponNumbers

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!--

               #. .. code-block:: none

                       Gets a string list of the valid weapon numbers

               #. .. code-block:: none

                     -->

               #. .. code-block:: none

                     <!-- If Weapons token property is empty set it to a default value -->

               #. .. code:: de2

                     [h,if(isPropertyEmpty("Weapons")): Weapons = "NumWeapons=0;"]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h: maxNum = getStrProp(Weapons, "NumWeapons")]

               #. .. code-block:: none

                     [h: wnumList=""]

               #. .. code-block:: none

                     [h,c(maxNum), code: {

               #. .. code:: de2

                       [h: wnum = roll.count+1]

               #. .. code-block:: none

                       [h: name = getStrProp(Weapons, strformat("Weapon%{wnum}Name"))]

               #. .. code-block:: none

                       [if(name != ""):

               #. .. code-block:: none

                         wnumList = listAppend(string(wnumList), string(wnum))

               #. .. code-block:: none

                       ]

               #. .. code:: de2

                     }]

               #. .. code-block:: none

                     [h: macro.return = wnumList]

         | 
         | The `string() <Macros:Functions:string>`__
           around the arguments in
           `listAppend() <Macros:Functions:listAppend>`__
           is to convert the arguments to strings, as of b48
           `listAppend() <Macros:Functions:listAppend>`__
           seems to have problems with arguments that could be
           interpreted as numbers.

         .. rubric:: Input Dialogs
            :name: input-dialogs

         So now we can get back to the dialogs. Lets create a dialog to
         edit weapons. Create a `macro
         button <Macro_Button>`__ on your
         `Lib:Test <Library_Token>`__ called
         EditWeaponDialog and paste the following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("weaponInput"): {

               #. .. code-block:: none

                       [h: weaponNum = getStrProp(macro.args, "Number")]

               #. .. code-block:: none

                       [h: name = getStrProp(macro.args, "Name")]

               #. .. code-block:: none

                       [h: bonus = getStrProp(macro.args, "Bonus")]

               #. .. code:: de2

                       [h: damage = getStrProp(macro.args, "Damage")]

               #. .. code-block:: none

                       <!-- If we do not have a weapon number grab the next one -->

               #. .. code-block:: none

                       [h, if(weaponNum == ""), code: {

               #. .. code-block:: none

                         [h,macro("NextWeaponNumber@this"): ""]

               #. .. code-block:: none

                         [h: weaponNum = macro.return]

               #. .. code:: de2

                       }]

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code-block:: none

                           <title>Edit Weapon Dialog</title>

               #. .. code-block:: none

                           <meta name="input" content="true">

               #. .. code:: de2

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <form name="weaponInput" action="[r:macroLinkText('AddWeapon@Lib:Test')]">

               #. .. code-block:: none

                             <table>

               #. .. code-block:: none

                               <tr>

               #. .. code:: de2

                                 <th>

               #. .. code-block:: none

                                   <label for="Name">Weapon Name</label>

               #. .. code-block:: none

                                 </th>

               #. .. code-block:: none

                                 <td>

               #. .. code-block:: none

                                   <input type="text" name="Name" value="[r: name]"></input> <br>

               #. .. code:: de2

                                 </td>

               #. .. code-block:: none

                               </tr>

               #. .. code-block:: none

                               <tr>

               #. .. code-block:: none

                                 <th>

               #. .. code-block:: none

                                   <label for="Damage">Weapon Damage</label>

               #. .. code:: de2

                                 </th>

               #. .. code-block:: none

                                 <td>

               #. .. code-block:: none

                                   <input type="text" name="Damage" value="[r: damage]"></input> <br>

               #. .. code-block:: none

                                 </td>

               #. .. code-block:: none

                               </tr>

               #. .. code:: de2

                               <tr>

               #. .. code-block:: none

                                 <th>

               #. .. code-block:: none

                                   <label for="Bonus">Weapon Bonus</label>

               #. .. code-block:: none

                                 </th>

               #. .. code-block:: none

                                 <td>

               #. .. code:: de2

                                   <input type="text" name="Bonus" value="[r: bonus]"></input>

               #. .. code-block:: none

                                 </td>

               #. .. code-block:: none

                               </tr>

               #. .. code-block:: none

                               </table>

               #. .. code-block:: none

                             <!-- hidden input with the weapon number -->

               #. .. code:: de2

                             <input type="hidden" name="Number" value="[r: weaponNum]"></input>

               #. .. code-block:: none

                      

               #. .. code-block:: none

                             <input type="submit" name="Save" value="Save"> </input>

               #. .. code-block:: none

                           </form>

               #. .. code-block:: none

                         </body>

               #. .. code:: de2

                       </html>

               #. .. code-block:: none

                     }]

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image8|

                  .. container:: thumbcaption

                     Edit Weapon Dialog

         | 
         | One thing to note is @this will not work in a macro link, so
           we build the @ portion of the macro to call when the form is
           submitted.

         The action=... portion of the form tag specifies which macro to
         call when any submit button is pushed for the form. If the
         dialog is specified as a input dialog, the close button down
         the bottom is not displayed and when any form on the dialog is
         submitted it is closed.

         The arguments to the macro that is called when the form is
         submitted is a string property list with the names of the input
         fields as the keys and the entered value as the values. Since I
         named all my inputs the same as the keys in the parameter for
         the AddWeaponMacro I can call that straight from the submit
         action on the form (some times is seems like I almost know what
         I am doing).

         The only problem is our edit weapon is kinda plain compared to
         our character sheet so time to add a little bling.

         Change your EditWeaponDialog `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("weaponInput"): {

               #. .. code-block:: none

                       [h: weaponNum = getStrProp(macro.args, "Number")]

               #. .. code-block:: none

                       [h: name = getStrProp(macro.args, "Name")]

               #. .. code-block:: none

                       [h: bonus = getStrProp(macro.args, "Bonus")]

               #. .. code:: de2

                       [h: damage = getStrProp(macro.args, "Damage")]

               #. .. code-block:: none

                       <!-- If we do not have a weapon number grab the next one -->

               #. .. code-block:: none

                       [h, if(weaponNum == ""), code: {

               #. .. code-block:: none

                         [h,macro("NextWeaponNumber@this"): ""]

               #. .. code-block:: none

                         [h: weaponNum = macro.return]

               #. .. code:: de2

                       }]

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code-block:: none

                           <title>Edit Weapon Dialog</title>

               #. .. code-block:: none

                           <meta name="input" content="true">

               #. .. code:: de2

                           <link rel="stylesheet" type="text/css" href="EditWeapon_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           <form name="weaponInput" action="[r:macroLinkText('AddWeapon@Lib:Test')]">

               #. .. code-block:: none

                             <table>

               #. .. code:: de2

                               <tr>

               #. .. code-block:: none

                                 <td>

               #. .. code-block:: none

                                   <table>

               #. .. code-block:: none

                                     <tr>

               #. .. code-block:: none

                                       <th>

               #. .. code:: de2

                                         <label for="Name">Weapon Name</label>

               #. .. code-block:: none

                                       </th>

               #. .. code-block:: none

                                       <td>

               #. .. code-block:: none

                                         <input type="text" name="Name" value="[r: name]">

               #. .. code-block:: none

                                         </input> <br>

               #. .. code:: de2

                                       </td>

               #. .. code-block:: none

                                     </tr>

               #. .. code-block:: none

                                     <tr>

               #. .. code-block:: none

                                       <th>

               #. .. code-block:: none

                                         <label for="Damage">Weapon Damage</label>

               #. .. code:: de2

                                       </th>

               #. .. code-block:: none

                                       <td>

               #. .. code-block:: none

                                         <input type="text" name="Damage" value="[r: damage]">

               #. .. code-block:: none

                                         </input> <br>

               #. .. code-block:: none

                                       </td>

               #. .. code:: de2

                                     </tr>

               #. .. code-block:: none

                                     <tr>

               #. .. code-block:: none

                                       <th>

               #. .. code-block:: none

                                         <label for="Bonus">Weapon Bonus</label>

               #. .. code-block:: none

                                       </th>

               #. .. code:: de2

                                       <td>

               #. .. code-block:: none

                                         <input type="text" name="Bonus" value="[r: bonus]">

               #. .. code-block:: none

                                         </input>

               #. .. code-block:: none

                                       </td>

               #. .. code-block:: none

                                     </tr>

               #. .. code:: de2

                                   </table>

               #. .. code-block:: none

                                 </td>

               #. .. code-block:: none

                                 <td>

               #. .. code-block:: none

                                   <img src='[r: getTokenImage(100)]'></img>

               #. .. code-block:: none

                                 </td>

               #. .. code:: de2

                               </tr>

               #. .. code-block:: none

                             </table>

               #. .. code-block:: none

                             <!-- hidden input with the weapon number -->

               #. .. code-block:: none

                             <input type="hidden" name="Number" value="[r: weaponNum]">

               #. .. code-block:: none

                             </input>

               #. .. code:: de2

                             <input id="saveButton" type="submit" name="Save" value="Save">

               #. .. code-block:: none

                             </input>

               #. .. code-block:: none

                           </form>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code:: de2

                     }]

         And add `macro button <Macro_Button>`__
         EditWeapon_css to `Lib:Test <Library_Token>`__
         that contains

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     body {

               #. .. code-block:: none

                        background-color: #CCBBBB

               #. .. code-block:: none

                     }

         And you might as well add a AddWeapon `macro
         button <Macro_Button>`__ to your
         `Token <Token>`__ that contains

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("EditWeaponDialog@Lib:Test"): "" ]

               #. .. code-block:: none

                     [abort(0)]

         Now our dialog looks like

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image9|

                  .. container:: thumbcaption

                     Edit Weapon Dialog with a Style Sheet

         Ok now lets make a quick dialog to display our weapons. Create
         a new `macro button <Macro_Button>`__ on your
         `Lib:Test <Library_Token>`__ called ViewWeapons
         and paste in the following

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [dialog("Weapons"): {

               #. .. code-block:: none

                       <html>

               #. .. code-block:: none

                         <head>

               #. .. code-block:: none

                           <title>Weapons</title>

               #. .. code:: de2

                           <link rel="stylesheet" type="text/css" href="ViewWeapon_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code-block:: none

                           [h,macro("GetWeaponNumbers@this"): ""]

               #. .. code-block:: none

                           [h: wpList = macro.return]

               #. .. code:: de2

                           <table>

               #. .. code-block:: none

                             [foreach(weapon, wpList, ""), code: {

               #. .. code-block:: none

                               [h,macro("GetWeapon@this"): weapon]

               #. .. code-block:: none

                               [h: wProp = macro.return]

               #. .. code-block:: none

                               <tr class="WeaponName">

               #. .. code:: de2

                                 <th>

               #. .. code-block:: none

                                   [r: getStrProp(wProp, "Name")]

               #. .. code-block:: none

                                 </th>

               #. .. code-block:: none

                               </tr>

               #. .. code-block:: none

                               <tr>

               #. .. code:: de2

                                 <th>Damage</th>

               #. .. code-block:: none

                                 <td>[r: getStrProp(wProp, "Damage")]</td>

               #. .. code-block:: none

                                 <th>Bonus</th>

               #. .. code-block:: none

                                 <td>[r: getStrProp(wProp, "Bonus")]</td>

               #. .. code-block:: none

                               </tr>

               #. .. code:: de2

                             }]

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code-block:: none

                     }]

         For good measure create a `macro
         button <Macro_Button>`__ called ViewWeapon_css on
         `Lib:Test <Library_Token>`__ paste in the
         following.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     .WeaponName {

               #. .. code-block:: none

                         background-color: #55AA55;

               #. .. code-block:: none

                         color: white;

               #. .. code-block:: none

                         text-align: center;

               #. .. code:: de2

                     }

         Add a `macro button <Macro_Button>`__ to your
         `Token <Token>`__ called ViewWeapons which
         contains.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("ViewWeapons@Lib:Test"): ""]

               #. .. code-block:: none

                     [abort(0)]

         | 
         | And this is what it looks like.

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image10|

                  .. container:: thumbcaption

                     Weapon List Dialog

         .. rubric:: Creating a Simple Character Sheet Frame
            :name: creating-a-simple-character-sheet-frame

         Up until now I havent talked at all about frames, but don't
         worry , change
         `[dialog():] <dialog_(roll_option)>`__ to
         `[frame():] <frame_(roll_option)>`__ above and it
         will work (except you cant have a frame that closes when you
         submit a form, what would be the point?).

         But lets make some final changes to show some frames, I am
         going to make all of these in one go as everything in them has
         been discussed previously in this post.

         First we are going to completely change the CharSheet `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("CharSheet"): {

               #. .. code-block:: none

                       [h: page = getStrProp(macro.args, "Page")]

               #. .. code-block:: none

                       [h,if(page==""): page="Main"]

               #. .. code-block:: none

                       <html>

               #. .. code:: de2

                         <head>

               #. .. code-block:: none

                           <title>Character Sheet</title>

               #. .. code-block:: none

                           <link rel="stylesheet" type="text/css" href="CharSheet_css@[r: getMacroLocation()]">

               #. .. code-block:: none

                         </head>

               #. .. code-block:: none

                         <body>

               #. .. code:: de2

                           [macro("CharSheetHeader@this"): page]

               #. .. code-block:: none

                           <br>

               #. .. code-block:: none

                           [macro("CharSheet"+page+"@this"): ""]

               #. .. code-block:: none

                         </body>

               #. .. code-block:: none

                       </html>

               #. .. code:: de2

                     }]

         Create a CharSheetHeader `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ and paste the
         following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: currentPage = macro.args]

               #. .. code-block:: none

                     [h: pages = "Main,Weapons"]

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       <tr>

               #. .. code:: de2

                         [foreach(page, pages,""), code: {

               #. .. code-block:: none

                           [h,if (page == currentPage): class="currentPage" ; class="page"]

               #. .. code-block:: none

                           [h: callback = "CharSheet@"+getMacroLocation()]

               #. .. code-block:: none

                           <td class="[r: class]">

               #. .. code-block:: none

                             [r: macroLink(page, callback, "none", "Page="+page)]

               #. .. code:: de2

                           </td>

               #. .. code-block:: none

                         }]

               #. .. code-block:: none

                       </tr>

               #. .. code-block:: none

                     </table>

         Create a CharSheetMain `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ and paste the
         following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: propNames = "Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma"]

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       <tr>

               #. .. code-block:: none

                         <td>

               #. .. code:: de2

                           <img src='[r: getTokenImage(100)]'></img>

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                         <td>

               #. .. code-block:: none

                           <table id="stats">

               #. .. code-block:: none

                             <tr>

               #. .. code:: de2

                               <th>Name</th>

               #. .. code-block:: none

                               <th>Score</th>

               #. .. code-block:: none

                             </tr>

               #. .. code-block:: none

                             [h: class = "oddRow"]

               #. .. code-block:: none

                             [foreach(prop, propNames, ""), code: {

               #. .. code:: de2

                               <tr class="[r:class]">

               #. .. code-block:: none

                                 <td>[r: prop]</td>

               #. .. code-block:: none

                                 <td>[r: getProperty(prop)]</td>

               #. .. code-block:: none

                               </tr>

               #. .. code-block:: none

                               [h: class = if(class=="oddRow", "evenRow", "oddRow")]

               #. .. code:: de2

                             }]

               #. .. code-block:: none

                           </table>

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                       </tr>

               #. .. code-block:: none

                     </table>

               #. .. code:: de2

                     <hr>

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       <tr>

               #. .. code-block:: none

                         <td>

               #. .. code-block:: none

                           [h: hpBarArgs = strformat("MaxLen=50; Value=%{HP}; MaxValue=%{MaxHP}; Label=HP")]

               #. .. code:: de2

                           [macro("TrafficLightBar@this"): hpBarArgs]

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                       </tr>

               #. .. code-block:: none

                       <tr>

               #. .. code-block:: none

                         <td>

               #. .. code:: de2

                           [h: hpBarArgs = strformat("MaxLen=50; Value=%{XP}; MaxValue=%{NextLevelXP}; Label=XP; Color=120,120,255")]

               #. .. code-block:: none

                           [macro("StatusBar@this"): hpBarArgs]

               #. .. code-block:: none

                         </td>

               #. .. code-block:: none

                       </tr>

               #. .. code-block:: none

                     </table>

         Create a CharSheetWeapons `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ and paste the
         following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,macro("GetWeaponNumbers@this"): ""]

               #. .. code-block:: none

                     [h: wpList = macro.return]

               #. .. code-block:: none

                     <table>

               #. .. code-block:: none

                       [foreach(weapon, wpList, ""), code: {

               #. .. code:: de2

                         [h,macro("GetWeapon@this"): weapon]

               #. .. code-block:: none

                         [h: wProp = macro.return]

               #. .. code-block:: none

                         <tr class="WeaponName">

               #. .. code-block:: none

                           <th>

               #. .. code-block:: none

                             [h: name = getStrProp(wProp, "Name")]

               #. .. code:: de2

                             [h: bonus = getStrProp(wProp, "Bonus")]

               #. .. code-block:: none

                             [h: damage = getStrProp(wProp, "Damage")]

               #. .. code-block:: none

                             [h: callback = "EditWeaponDialog@" + getMacroLocation()]

               #. .. code-block:: none

                             [h: args = strformat("Number=%{weapon}; Name=%{name}; Damage=%{damage}; Bonus=%{bonus}")]

               #. .. code-block:: none

                             [r: macroLink(name, callback, "none", args)]

               #. .. code:: de2

                           </th>

               #. .. code-block:: none

                         </tr>

               #. .. code-block:: none

                         <tr>

               #. .. code-block:: none

                           <th>Damage</th>

               #. .. code-block:: none

                           <td>[r: getStrProp(wProp, "Damage")]</td>

               #. .. code:: de2

                           <th>Bonus</th>

               #. .. code-block:: none

                           <td>[r: getStrProp(wProp, "Bonus")]</td>

               #. .. code-block:: none

                         </tr>

               #. .. code-block:: none

                       }]

               #. .. code-block:: none

                     </table>

         And the last change to make is the CharSheet_css `macro
         button <Macro_Button>`__ on
         `Lib:Test <Library_Token>`__ an paste the
         following into it.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     .oddRow { background-color: #FFFFFF }

               #. .. code-block:: none

                     .evenRow { background-color: #EEEEAA }

               #. .. code-block:: none

                     #stats th { background-color: #113311; color: #FFFFFF }

               #. .. code-block:: none

                     .WeaponName a {

               #. .. code:: de2

                         background-color: #55AA55;

               #. .. code-block:: none

                         color: white;

               #. .. code-block:: none

                         text-align: center;

               #. .. code-block:: none

                     }

               #. .. code-block:: none

                     .page a {

               #. .. code:: de2

                        background-color: #5555CC;

               #. .. code-block:: none

                        color: white;

               #. .. code-block:: none

                     }

               #. .. code-block:: none

                     .currentPage a {

               #. .. code-block:: none

                        background-color: #7777FF;

               #. .. code:: de2

                        color: white;

               #. .. code-block:: none

                     }

         So what does this give us? A shiny new frame. Unlike Dialogs,
         Frames act like any of the other maptool windows and can be
         docked on the sides, or with other windows (forming a tab).

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image11|

                  .. container:: thumbcaption

                     Simple Character Sheet in a Frame

         | 
         | Where it says Main and Weapons on the top, they are links, if
           you click on Weapons it will change the CharacerSheet frame
           to

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image12|

                  .. container:: thumbcaption

                     Weapon List in a Frame

         And as an added bonus, the weapon names are links, if you click
         on them it will open up the edit dialog where you can edit
         them. (note this will not update the character sheet at this
         time, but that is left as an exercise for the reader).

         This has just been a short example of what can be done, I am
         sure people will come up with some great ideas how to use this.

         The campaign file with the dialogs we have created can be found
         at
         `campaign <http://lmwcs.com/maptool/campaigns/B48MiniTuts.cmpgn>`__

         .. rubric:: Related Pages
            :name: related-pages

         -  `Supported CSS
            Styles <Supported_CSS_Styles>`__
         -  `Forms tutorial <Forms_tutorial>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Dialogs_and_Frames&oldid=6905"

