=================================================
Creating Macro Buttons Using a Macro - MapToolDoc
=================================================

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

   .. rubric:: Creating Macro Buttons Using a Macro
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

            -  `1 Introduction <#Introduction>`__

               -  `1.1 Assumptions <#Assumptions>`__

            -  `2 Macro Code and
               Explanation <#Macro_Code_and_Explanation>`__

               -  `2.1 Receiving Arguments and Assigning
                  Variables <#Receiving_Arguments_and_Assigning_Variables>`__
               -  `2.2 Requesting User Input <#Requesting_User_Input>`__
               -  `2.3 Checking for the Power's Use Limits and Setting
                  Colors <#Checking_for_the_Power.27s_Use_Limits_and_Setting_Colors>`__
               -  `2.4 Building the Macro Button
                  Contents <#Building_the_Macro_Button_Contents>`__
               -  `2.5 Creating the Macro
                  Button <#Creating_the_Macro_Button>`__
               -  `2.6 Mop-Up <#Mop-Up>`__

            -  `3 The Result <#The_Result>`__
            -  `4 See Also <#See_Also>`__

         .. rubric:: Introduction
            :name: introduction

         The following tutorial illustrates one method of creating macro
         buttons for a token based on user input. In this particular
         case, the macros illustrated below are used to configure a new
         token with several buttons illustrating different powers that
         the character represented by the token possesses. The tutorial
         is directly applicable to the *Dungeons & Dragons 4th Edition*
         game system, but the concepts in it may be applicable to other
         game systems. This tutorial may also be useful in conjunction
         with the tutorials on changing macro buttons.

         .. rubric:: Assumptions
            :name: assumptions

         The button creation macro illustrated below is actually one
         component of a much larger sequence of macros, so in order to
         understand what is happening, there are a few assumptions to be
         made.

         1. Powers in this campaign setup are stored in a series of
         `token properties <Token:token_property>`__ with
         the names "Power0", "Power1", "Power2", and so on. These token
         properties contain power information in the form of a `string
         property list <Macros:string_property_list>`__
         with the format:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     powername=Melee Basic Attack ; action=standard ; usage=at-will ; attack=5 ;

               #. .. code-block:: none

                     against=AC ; targets=one creature ; damage=1d6+5 ; critdamage=11 ; damtype= ;

               #. .. code-block:: none

                     hitEffect=--none-- ; missEffect=--none-- ; atktype=melee ;

               #. .. code-block:: none

                     range=weapon ; expended=Available ; reliable=0 ; special=--none-- ;

         2. This macro will receive from a calling macro an argument
         called
         `macro.args <Macros:Special_Variables:macro.args>`__
         that contains a number (which will be used to determine which
         power - Power0, Power1, etc. - will have a new button created).

         3. This macro in particular is the final step in a macro
         sequence, so it is assumed that when this macro is called, the
         string property list for the power in question has already been
         populated.

         .. rubric:: Macro Code and Explanation
            :name: macro-code-and-explanation

         The `full macro
         code <Tutorials:Macros:create_buttons_full_code>`__
         is broken down and explained below.

         .. rubric:: Receiving Arguments and Assigning Variables
            :name: receiving-arguments-and-assigning-variables

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:powerSlot=macro.args]

               #. .. code-block:: none

                     [h:pname=getStrProp(eval("Power"+powerSlot),"powername")]

               #. .. code-block:: none

                     [h:use=getStrProp(eval("Power"+powerSlot),"usage")]

         This section of the macro simply assigns the value of
         *macro.args* to a new variable, *powerSlot*. The variable
         *powerSlot* is then used in line 2 to extract the name of the
         power (the *powername* key in the string property) and assign
         it to *pname*, and to extract the *usage* value from the string
         property as well.

         .. rubric:: Requesting User Input
            :name: requesting-user-input

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:status=input(

               #. .. code-block:: none

                         "addButtons|Yes,No|Add Macro Buttons to your token?|RADIO|ORIENT=H SELECT=1"

               #. .. code-block:: none

                     )]

               #. .. code-block:: none

                     [h:abort(status)]

         This section is a simple
         `input() <Macros:Functions:input>`__ function
         that confirms whether the user wants to add the button to their
         token's macro set. This is important because if a macro button
         is already present, this macro will create a duplicate.
         Frequently, however, users will want to simply update their
         power information, rather than create a new button.

         .. rubric:: Checking for the Power's Use Limits and Setting
            Colors
            :name: checking-for-the-powers-use-limits-and-setting-colors

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [IF(addButtons==0),CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                     [h,SWITCH(use),CODE:

               #. .. code-block:: none

                     case "at-will":

               #. .. code:: de2

                     {

               #. .. code-block:: none

                       [bcolor="green"]

               #. .. code-block:: none

                       [fcolor="black"]

               #. .. code-block:: none

                       [group="1: Powers - At-Will"]

               #. .. code-block:: none

                       [grayout=0]

               #. .. code:: de2

                     };

               #. .. code-block:: none

                     case "encounter":

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                       [bcolor="red"]

               #. .. code-block:: none

                       [fcolor="white"]

               #. .. code:: de2

                       [group="2: Powers - Encounter"]

               #. .. code-block:: none

                       [grayout=1]

               #. .. code-block:: none

                     };

               #. .. code-block:: none

                     case "daily":

               #. .. code-block:: none

                     {

               #. .. code:: de2

                       [bcolor="black"]

               #. .. code-block:: none

                       [fcolor="white"]

               #. .. code-block:: none

                       [group="3: Powers - Daily"]

               #. .. code-block:: none

                       [grayout=1]

               #. .. code-block:: none

                     };

               #. .. code:: de2

                     case "recharge":

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                       [bcolor="blue"]

               #. .. code-block:: none

                       [fcolor="white"]

               #. .. code-block:: none

                       [group="3: Powers - Recharging"]

               #. .. code:: de2

                       [grayout=1]

               #. .. code-block:: none

                     };]

         This is probably the most complex piece of the macro: a
         `SWITCH() <Macros:Branching_and_Looping#SWITCH_Option>`__
         roll option nested inside an
         `IF() <Macros:Branching_and_Looping#IF_Option>`__
         option, both of which use the `CODE:{
         } <Macros:Branching_and_Looping#CODE>`__ option
         to execute multiple macro commands as a single block.

         However, functionally, this segment's purpose is to assign
         several variables (to be used later) based on whether the power
         is an at-will, encounter, daily, or rechargeable power;
         remember that this entire SWITCH() block is contained within
         the first code block of the IF() statement.

         .. rubric:: Building the Macro Button Contents
            :name: building-the-macro-button-contents

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:macroProps="autoexec=true;"]

               #. .. code-block:: none

                     [h:macroProps=setStrProp(macroProps,"color",bcolor)]

               #. .. code-block:: none

                     [h:macroProps=setStrProp(macroProps,"fontColor",fcolor)]

               #. .. code-block:: none

                     [h:macroProps=setStrProp(macroProps,"group",group)]

               #. .. code:: de2

                     [h:grayoutString=""]

               #. .. code-block:: none

                     [h,IF(grayout): grayoutString=encode("[h:setMacroProps(" + "'" +pname+ "'" + ",'color=gray;' " + ")]")]

               #. .. code-block:: none

                     [h:command=encode("[h:thisPower="+"'"+pname+"'"+"]")]

               #. .. code-block:: none

                     [h:command=command+encode("[h:index=getMacroIndexes(thisPower)]")]

               #. .. code-block:: none

                     [h:command=command+encode("[h:mProps=getMacroProps(index)]")]

               #. .. code:: de2

                     [h:command=command+encode("[h:color=getStrProp(mProps,'color')]")]

               #. .. code-block:: none

                     [h:command=command+encode("[h:used=if(color=='gray', 0, 1)]")]

               #. .. code-block:: none

                     [h:command=command+encode("[h:abort(used)]")]

               #. .. code-block:: none

                     [h:command=command + encode("[MACRO('AttackMain@Lib:test'):thisPower]")]

               #. .. code-block:: none

                     [h:command=command+grayoutString]

         This sequence may appear confusing, but it is conceptually
         relatively simple. Because a macro button must contain macro
         instructions, this segment of macro code builds a string using
         the `encode() <Macros:Functions:encode>`__
         function.

         In this case, **encode()** is used because macro commands
         require the square bracket ([ ]), but the macro parser has a
         tendency to attempt to evaluate anything in square brackets as
         a command, which - if you get a quotation mark out of place -
         will cause various frustrating and eldritch errors. To prevent
         this, we use single and double quotation marks to ensure that
         each element of the final string is treated as a string, and
         then **encode()** the whole result to a single string.

         Specifically:

         -  Lines 1-4 set the macro properties based on the output of
            the earlier **SWITCH()** statement, each step adding an
            additional key-value pair to the macro property string.
         -  Lines 5-6 check to see if the *grayout* variable is true,
            and if so create an encoded string adding a command to
            change the color of the button to gray when the button is
            clicked.
         -  Lines 7-1 iteratively assemble the *command* variable as an
            encoded string (the steps are broken down to make sure that
            the strings are handled properly by the parser). These steps
            create a sequence of commands that will, when the user
            clicks the button:

         #. Call a macro on a `library
            token <Token:library_token>`__ to resolve the
            use of the power
         #. If the macro is an encounter or daily power, change the
            macro button color to gray
         #. If the macro is an encounter or daily power, prevent the
            macro from executing if the button is clicked again

         .. rubric:: Creating the Macro Button
            :name: creating-the-macro-button

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:createMacro(pname, decode(command), macroProps)]

               #. .. code-block:: none

                     Buttons added.

               #. .. code-block:: none

                     };

         This step is the easy part! We call the
         `createMacro() <Macros:Functions:createMacro>`__
         function and pass the arguments *pname* (containing the power's
         name), the `decoded <Macros:Functions:decode>`__
         *command* string (containing all of the macro commands we wish
         the new button to contain), and the variable *macroProps*
         (which sets the initial button and font colors, group, and
         other properties we wish the new button to have).

         Note that line three contains the closing brace of this CODE()
         block - be sure to close your CODE blocks properly!

         .. rubric:: Mop-Up
            :name: mop-up

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                     No buttons added to token.

               #. .. code-block:: none

                     };]

         This tiny section at the very end is what is executed if the
         user does *not* wish to add buttons to their token. It is the
         *false_body* of the IF(), and will simply echo "No buttons
         added to token." to the chat window.

         .. rubric:: The Result
            :name: the-result

         When this macro is finished processing, the end result is that
         the token in question should have a new macro button generated
         containing the command sequence we assembled in the *command*
         variable. An example of the output - using the sample string
         property list shown in the
         `Assumptions <Tutorials:Macros:CreatingMacroButtons#Assumptions>`__
         section - is shown below:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:thisPower='Melee Basic Attack']

               #. .. code-block:: none

                     [MACRO('AttackMain@Lib:test'):thisPower]

         Another sample, this one including the *grayout* power
         information as well as the additional code to prevent repeat
         execution of the macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:thisPower='Chain Lightning']

               #. .. code-block:: none

                     [h:index=getMacroIndexes(thisPower)]

               #. .. code-block:: none

                     [h:mProps=getMacroProps(index)]

               #. .. code-block:: none

                     [h:color=getStrProp(mProps,'color')]

               #. .. code:: de2

                     [h:used=if(color=='gray', 0, 1)]

               #. .. code-block:: none

                     [h:abort(used)]

               #. .. code-block:: none

                     [MACRO('AttackMain@Lib:test'):thisPower]

               #. .. code-block:: none

                     [h:setMacroProps('Chain Lightning','color=gray;' )]

         **NOTE**: Although I have introduced line breaks in the
         examples above for ease of reading, the actual commands in the
         macro button do not have any line breaks between them. It
         requires some relatively convoluted use of strings and string
         concatenation to create easy-to-read command sequences via
         `createMacro() <createMacro>`__. Future builds of
         MapTool should remedy this situation.

         .. rubric:: See Also
            :name: see-also

         `createMacro() <createMacro>`__,
         `setMacroCommand() <setMacroCommand>`__,
         `setMacroProps() <setMacroProps>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Creating_Macro_Buttons_Using_a_Macro&oldid=3726"

