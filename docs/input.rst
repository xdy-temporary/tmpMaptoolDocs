==================
input - MapToolDoc
==================

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

   .. rubric:: input
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

            -  `1 input() Function <#input.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Input Types and
                  Options <#Input_Types_and_Options>`__

                  -  `1.2.1 TEXT <#TEXT>`__

                     -  `1.2.1.1 TEXT Options <#TEXT_Options>`__

                  -  `1.2.2 LIST <#LIST>`__

                     -  `1.2.2.1 LIST Options <#LIST_Options>`__

                  -  `1.2.3 CHECK <#CHECK>`__

                     -  `1.2.3.1 CHECK Options <#CHECK_Options>`__

                  -  `1.2.4 RADIO <#RADIO>`__

                     -  `1.2.4.1 RADIO Options <#RADIO_Options>`__

                  -  `1.2.5 LABEL <#LABEL>`__

                     -  `1.2.5.1 LABEL Options <#LABEL_Options>`__

                  -  `1.2.6 PROPS <#PROPS>`__

                     -  `1.2.6.1 PROPS Options <#PROPS_Options>`__

                  -  `1.2.7 TAB <#TAB>`__

                     -  `1.2.7.1 TAB Options <#TAB_Options>`__

               -  `1.3 Examples <#Examples>`__

         .. rubric:: input() Function
            :name: input-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Allows the user to input several values at once via a modal
            dialog. The function takes one or more string arguments, one
            for each variable requiring assignment. Execution of the
            calling macro is paused while waiting for the user to
            interact with the input dialog.
            Returns ``1`` if the user clicked the **OK** button, or
            ``0`` if they clicked **Cancel** (or hit **Esc** to exit the
            dialog). If ``input()`` returns ``0``, no variable
            assignments were made.

            Note that there are no built-in mechanisms for input
            validation for ``TEXT`` input types.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     input(inputField, ..., ...)

         **Parameters**

         -  ``inputField`` - A string containing various
            'sub-parameters' that set the type and options of each
            ``inputField``; requires at least one ``inputField`` but
            will accept a reasonably large amount. The ``inputField``\ s
            can be set using a series of individual parameters, or as
            one or more `String Lists </rptools/wiki/String_List>`__. If
            a `String List </rptools/wiki/String_List>`__ is used, the
            delimiter must be ``"##"``. This allows, among other things,
            for more dynamic input menus, with the number and type of
            input requests customized to the circumstances. Normally,
            each line is described by a string, wrapped in quotes, and
            the strings are separated by commas. The input function
            looks for unquoted commas to determine which strings are
            intended to be read as line entries. The function, however,
            can also recognize ``##`` as a denotation of such a line
            break. Since this denotation can be surrounded by quotes
            more easily, it is possible to have a single string, wrapped
            in quotes, describe multiple input requests. The strings can
            be compiled in any number of ways: for instance using
            `listAppend() </rptools/wiki/listAppend>`__ and setting the
            delimiter to ``"##"``. Strings involving these ``##``'s can
            be intermixed with other standard strings. See the example
            below.

         You declare the 'sub-parameters' of each ``inputField`` in the
         following manner:

         -  ``"variableName|value|prompt|inputType|options"``

         **Sub-Parameters**

         -  ``variableName`` - The name of the variable to which the
            value of the ``inputField`` is assigned.
         -  ``value`` - The initial value present in the dialog box. If
            not present, it defaults to ``0``. In some cases you use a
            special syntax to indicate multiple values.
         -  ``prompt`` - The prompt displayed to the user to indicate
            the meaning of the ``inputField``.
         -  ``inputType`` - Describes the type of input control
            presented to the user. Each of the different types are
            described in more detail below.
         -  ``options`` - Contains one or more options that control the
            appearance of the input control or how information entered
            in the control is treated; options are given in the format
            ``option=value`` and separated by a space.

         .. rubric:: Input Types and Options
            :name: input-types-and-options

         .. rubric:: TEXT
            :name: text

         Creates a text box containing the ``value`` or ``0``. The
         contents typed in the box are assigned to the variable, and
         there is no limit to the length of the data that can be
         entered.

         .. rubric:: TEXT Options
            :name: text-options

         -  ``WIDTH=nnn`` - Sets the width of the text box; defaults to
            ``WIDTH=16``.
         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as a tooltip.

         --------------

         .. rubric:: LIST
            :name: list

         Creates a drop-down list of choices. The variable is assigned
         the index (starting at ``0``) of the item that was selected.
         The ``value`` sub-parameter is a comma delimited list of the
         values that can be chosen.

         .. rubric:: LIST Options
            :name: list-options

         -  ``SELECT=nnn`` - Sets the index of the initial selection in
            the drop-down list (the first item is number ``0``);
            defaults to ``SELECT=0``.
         -  ``VALUE=STRING`` - The variable is assigned the string
            contents of the selected item instead of the index; defaults
            to ``VALUE=NUMBER``.
         -  ``ICON=TRUE`` - If the string for the item contains a space
            and then an image asset URL, the image is displayed in the
            entry; defaults to ``ICON=FALSE``. Text before the URL is
            used for the entry's text. The
            `getTokenImage() </rptools/wiki/getTokenImage>`__ and
            `getStateImage() </rptools/wiki/getStateImage>`__ functions
            can be used to obtain asset URLs.
         -  ``ICONSIZE=nnn`` - The size the icons; defaults to
            ``ICONSIZE=50``. All icons are stretched to fit a square
            this size. If the asset URL points to an image that is not
            square, some distortion will occur.
         -  ``TEXT=FALSE`` - No text is shown in the list entries next
            to the icons; defaults to ``TEXT=TRUE``, and is ignored if
            no icon is set.
         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as a tooltip.

         --------------

         .. rubric:: CHECK
            :name: check

         Creates a checkbox. The variable is assigned either ``0``
         (unchecked) or ``1`` (checked).

         .. rubric:: CHECK Options
            :name: check-options

         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as a tooltip.

         --------------

         .. rubric:: RADIO
            :name: radio

         Creates a group of radio buttons. This option works much like
         ``LIST``, returning the index of the choice that was selected.

         .. rubric:: RADIO Options
            :name: radio-options

         -  ``ORIENT=H`` - Arranges the radio buttons horizontally on a
            single line; defaults to ``ORIENT=V``.
         -  ``SELECT=nnn`` - Sets the initially selected radio button
            (the first item is number ``0``); defaults to ``SELECT=0``.
         -  ``VALUE=STRING`` - The variable is assigned the string
            contents of the selected item instead of the index; defaults
            to ``VALUE=NUMBER``.
         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as title placed in the border of the radio button
            group.

         --------------

         .. rubric:: LABEL
            :name: label

         Creates a static label. The ``variableName`` is ignored, and
         nothing is assigned to it.

         .. rubric:: LABEL Options
            :name: label-options

         -  ``ICON=TRUE`` - If the string for the ``value`` contains a
            space and then an image asset URL, the image is displayed;
            defaults to ``ICON=FALSE``.
         -  ``ICONSIZE=nnn`` - The size the icon; defaults to
            ``ICONSIZE=50``. The icon is stretched to fit a square this
            size. If the asset URL points to an image that is not
            square, some distortion will occur.
         -  ``TEXT=FALSE`` - The ``value`` is not shown; defaults to
            ``TEXT=TRUE``.
         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as a tooltip.

         --------------

         .. rubric:: PROPS
            :name: props

         Creates a bordered sub-area containing multiple text boxes, one
         for each entry in a `String Property
         List </rptools/wiki/String_Property_List>`__ stored in
         ``value``. The ``variableName`` is assigned a new string
         property containing all the entries with their updated values.

         .. rubric:: PROPS Options
            :name: props-options

         -  ``SETVARS=SUFFIXED`` - Makes a variable assignment for each
            of the sub-values, with an underscore appended to the name;
            defaults to ``SETVARS=NONE``.
         -  ``SETVARS=UNSUFFIXED`` - Makes variable assignments to
            unmodified variable names. ``SUFFIXED`` is usually
            preferred, unless you are not using variable names that
            match `Token Properties </rptools/wiki/Token_Property>`__ or
            if you specifically intend to overwrite them.
         -  ``SPAN=TRUE`` - Causes the ``prompt`` to be hidden and
            allows the ``inputField`` to span the width of the dialog;
            defaults to ``SPAN=FALSE``. If hidden the ``prompt`` text is
            used as title placed in the border of the ``PROPS`` group.

         --------------

         .. rubric:: TAB
            :name: tab

         Creates a tab for a tabbed dialog box. The ``variableName``
         variable gets assigned a `String Property
         List </rptools/wiki/String_Property_List>`__ containing all the
         variable assignments made on this tab. Since some of the
         variables may be property strings themselves, the tab property
         string uses the non-default delimiter ``"##"``. When using
         tabs, the first ``inputField`` must be a ``TAB``.

         .. rubric:: TAB Options
            :name: tab-options

         -  ``SELECT=TRUE`` - Causes this tab to be displayed when the
            dialog appears; defaults to ``SELECT=FALSE``.

         --------------

         **TAB Example**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [H: input(

               #. .. code:: de1

                          "tab0 | Info || TAB", 

               #. .. code:: de1

                          "Name ## Rank ## Serial number | 1,2,3 || LIST",

               #. .. code:: de1

                          "tab1 | Abilities || TAB", 

               #. .. code:: de2

                          "Strength ## Dexterity ## Wisdom"

               #. .. code:: de1

                     )]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **1. A simple input() requesting 3 different text
            variables.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [input("AtkBonus", "DmgBonus", "CombatAdvantage")]

            Displays:

            |simple-input.jpg|

            Note that only the ``variableName`` is required to generate
            an input dialog - if that is all that is provided,
            ``input()`` assumes that each ``variableName`` will be
            assigned using a text field.

            **2. A more complex input, including LABEL, CHECK, and TEXT
            fields.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:status=input(

                  #. .. code:: de1

                            "junkVar|"+powerClicked+"|Selected Power|LABEL",

                  #. .. code:: de1

                            "ComAdv|0|Combat Advantage|CHECK",

                  #. .. code:: de1

                            "MarkPenalty|0|Marked by an enemy other than your target|CHECK",

                  #. .. code:: de2

                            "TargetConcealed|0|Target has Concealment|CHECK",

                  #. .. code:: de1

                            "MiscBonus|0|Miscellaneous BONUSES to your attack roll",

                  #. .. code:: de1

                            "MiscPenalty|0|Miscellaneous PENALTIES to your attack roll",

                  #. .. code:: de1

                            "mdb|0|Miscellaneous BONUS to Damage")]

                  #. .. code:: de1

                        [h:abort(status)]

            Displays:

            |Input-checksntext.jpg|

            Recall that ``junkVar``, as the ``variableName`` for a
            ``LABEL`` control, has no value assigned to it. In this
            example, we assume ``powerClicked`` is a variable that is
            passed in some fashion to the macro generating this input.
            It is incorporated using the standard method of
            concatenating a variable into a string
            (``"string text"+variable+"more string text"``). Finally,
            observe that the variable ``status`` is assigned the value
            returned by the ``input()`` function, and the
            `abort() </rptools/wiki/abort>`__ function is called using
            the value of ``status``. In this fashion, the macro is
            terminated if the user clicks the **Cancel** button or hits
            the **ESC** key.

            **3. An input showing several LIST boxes, as well as the
            VALUE=STRING option.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:status=input(

                  #. .. code:: de1

                            "targetNum|"+imgList+"|Select Target|LIST|SELECT=0 ICON=TRUE ICONSIZE=30",

                  #. .. code:: de1

                            "feature|Hunter's Quarry, Sneak Attack, Warlock's Curse|Type of Striker Damage|LIST|SELECT=0 VALUE=STRING",

                  #. .. code:: de1

                            "CQSDice|1d6,1d8,2d6,2d8,3d6,3d8|Curse, Quarry, or Sneak Attack Dice|LIST|SELECT=0 VALUE=STRING",

                  #. .. code:: de2

                            "critAttack|0|Was the attack a critical hit?|CHECK"

                  #. .. code:: de1

                        )]

            Displays:

            |Input-lists.jpg|

            Note that the ``prompt`` section for each list contains a
            list of items, *or* a variable containing a `String
            List </rptools/wiki/String_List>`__ (*e.g.*, the variable
            ``imgList``). In the first list, the ``ICON`` and
            ``ICONSIZE`` options are set, because that list contains
            image asset URLs for token images. In the second two lists,
            the ``VALUE=STRING`` option is set so that the value in the
            corresponding variable is the actual string (*e.g.*
            ``"Sneak Attack"``) rather than the index of the list item.

            **4. An input using the "##" delimiter trick.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:inptext=""]

                  #. .. code:: de1

                        [h:num=1]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        [h,foreach(entry,"SPD1,SPD2,SPD3,SPD4,SPD5,SPD6,SPD7,SPD8,SPD9"),code:{

                  #. .. code:: de2

                          [if(num<=CMSL),code:{

                  #. .. code:: de1

                            [inptext=listAppend(inptext,entry+"|"+eval(entry)+"|Level "+num,"##")]

                  #. .. code:: de1

                          }]

                  #. .. code:: de1

                          [num=num+1]

                  #. .. code:: de1

                        }]

                  #. .. code:: de2

                         

                  #. .. code:: de1

                        [h:screen0=input(

                  #. .. code:: de1

                          "junkvar|Include any bonus spells from high Wisdom|Enter your Cleric spells per day|LABEL",

                  #. .. code:: de1

                          inptext

                  #. .. code:: de1

                        )]

            In this example, variables ``SPD1-SPD9`` and ``CMSL`` are
            called earlier from a token and represent spells per day for
            spell levels 1-9 and the maximum spell level accessible by
            the token at the moment for the class in question. The macro
            is intended to allow manual changing of the number of spells
            per day for the token, but the input is cleaned up and
            prevents complications by not allowing for inputs to spell
            levels beyond what is available. The first line in the input
            is a standard string, followed by a comma. The second is a
            ``"##"``-containing string set by the
            `[foreach():] </rptools/wiki/foreach_(roll_option)>`__
            function above, which will contain just the number of input
            requests, separated by ``##``'s, needed in the situation.

            **5. A much more elegant and way more sophisticated way to
            example no. 4 is aliasmaks(?) strformat/json.evaluate
            trick** If you are in need of an ``input()`` function where
            the number of inputs can vary like in ex. 4, you can also
            opt to use a json array and use
            `json.evaluate() </rptools/wiki/json.evaluate>`__. This will
            look as follows:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- Define local vars -->

                  #. .. code:: de1

                        [H: Strength = 12]

                  #. .. code:: de1

                        [H: Toughness = 14]

                  #. .. code:: de1

                        [H: Hitpoints = 20]

                  #. .. code:: de2

                        [H: statList = "Strength, Toughness, Hitpoints"]

                  #. .. code:: de1

                        [H: inputStr = "[]"]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        <!-- Build input form simple -->

                  #. .. code:: de1

                        [H: inputStr = json.append(inputStr,"junk|<html><b>A simple example</b></html>|-|LABEL|SPAN=TRUE")]

                  #. .. code:: de2

                        [H: inputStr = json.append(inputStr, "Strength|"+Strength+"|Enter Strenght value")]

                  #. .. code:: de1

                        [H: inputStr = json.append(inputStr, "Toughness|"+Toughness+"|Enter Toughness value")]

                  #. .. code:: de1

                        [H: inputStr = json.append(inputStr, "Hitpoints|"+Hitpoints+"|Entere number of Hitpoints")]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        <!-- Build input form advanced -->

                  #. .. code:: de2

                        [H: inputStr = json.append(inputStr,"junk|<html><b>A complex example</b></html>|-|LABEL|SPAN=TRUE")]

                  #. .. code:: de1

                        [H, foreach(stat,statList): inputStr = json.append(inputStr,strformat("%{stat}|%s|<html><b><font color=blue>Enter %{stat} value</b></font></html>|TEXT|WIDTH=6", eval(stat)))]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        <!-- put local variables in input form -->

                  #. .. code:: de1

                        [H: inputStr = json.evaluate(inputStr)]

                  #. .. code:: de2

                         

                  #. .. code:: de1

                        <!-- get user input -->

                  #. .. code:: de1

                        [H: hasInput = input(json.toList(inputStr,"##"))]

            **6. An input using aliasmask's no-zero-trick** Usually,
            when you leave a value blank for input it puts that annoying
            ``0`` in it's place. Here's one way to avoid that. The only
            limitation, I suppose is that the variable name is visible
            as the prompt (and the variable name/contents must be
            StrProp-compatible).

            *(thanks to aliasmask for the trick and biodude for stating
            the limits.)*

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:abort(input(

                  #. .. code:: de1

                            "junk|<html><b>Enter player names. These should match the user names:<br><font color='red'>"+getAllPlayerNames()+"</font></html>|-|LABEL|SPAN=TRUE",

                  #. .. code:: de1

                          "Enter Player Names|player0=;player1=;player2=||PROPS|SPAN=TRUE SETVARS=UNSUFFIXED"

                  #. .. code:: de1

                        ))]

            **7. An input using Wolph42's tooltip-trick** It is possible
            to use HTML mark up by just adding HTML tags around the
            input text. This makes it possible to use e.g. bold and
            italic tags, but also the ``span`` tag. This span tag allows
            tooltips to be added anywhere via its ``title`` attribute.
            Here's an example:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [H: hasInput = input(

                  #. .. code:: de1

                        "junk|<html>Some title text</html>|<html>here comes the tooltip text</html>|LABEL|SPAN=TRUE",

                  #. .. code:: de1

                        "someVariable|0|<html><span title='<html>This text will be shown as a tooltip if you hover with your mouse over the text</html>'>Do you wish to turn the <b>setting</b> on?</span></html>|CHECK"

                  #. .. code:: de1

                        )]

            Another interesting trick is adding pictures to the input.
            This example show the image of the selected token:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:input(

                  #. .. code:: de1

                            "junk|<html><b>Show picture of token<br></html>|-|LABEL|SPAN=TRUE",

                  #. .. code:: de1

                         "junk|<html><img src='"+getTokenImage(60)+"'></img></html>|-|LABEL|SPAN=TRUE"

                  #. .. code:: de1

                        )]

            | 

            .. container:: template_note

               **b89 (b90 also ?)**: **input()** no longer *eats* the
               colon ``':'``. And as the
               `getTokenImage() </rptools/wiki/getTokenImage>`__ will
               return ``'asset://....'`` this will fail.

            ∗

            ::

               It might get fixed in b90 but if not there is a workaround. Just change the last line into:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        "junk|<html><img src='"+replace(getTokenImage(), ":", "&#58;")+"' height=60 width=60></img></html>|-|LABEL|SPAN=TRUE"

            If you really want to go full monty on the tooltip INSIDE
            the input, here's an example of what is possible (the wiki
            can't properly handle all the code here so it comes out a
            bit funky):

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:hasInput     = input('

                  #. .. code:: de1

                            someVariable|0|<html><span title="<html>

                  #. .. code:: de1

                          This setting allows for more advanced use of the movement limiter. First off: <b>In order for this to work <i>Limit Movement</i> must be<br>

                  #. .. code:: de1

                          set to a number other then 0(the actual number wont be used).</b> If you enter 0 here then this setting will be ignored and the movement<br>

                  #. .. code:: de2

                          will be limited to what you have set in <i>Limit Movement</i>.<br>

                  #. .. code:: de1

                          <br>

                  #. .. code:: de1

                            <b>Example of how to use this setting:</b><br>

                  #. .. code:: de1

                          Let say that all the tokens have a characteristic: <i>Dexterity</i> and the max amount of cells a token is allowed to move is 4 x <i>Dexterity</i>.<br>

                  #. .. code:: de1

                         Then what you set here is: <font bgcolor=white color=gray>[r:4*Dexterity]</font> You can enter any piece of code in here, as long as the output of that code<br>

                  #. .. code:: de2

                            results in a number. The token that is moved will be the currentToken for this code! Note that if multiple tokens are moved, the first selected<br>

                  #. .. code:: de1

                           token will be the currentToken.<br>

                  #. .. code:: de1

                           <br>

                  #. .. code:: de1

                          <b>Adding states and changing the output message</b>.<br>

                  #. .. code:: de1

                         You can take this code even a step further and also change the output to the chat. This can be done by setting the predefined message variable to<br>

                  #. .. code:: de2

                         something else. Here you can make use of other predefined variables as well. The default message is:<br>

                  #. .. code:: de1

                          <font bgcolor=white color=gray>[h:message = &quot;You moved %{tok} %{usedMove} cells. The maximum allowed movement is %{limitMovement} cells.&quot;]</font><br>

                  #. .. code:: de1

                           (HTML make up can be used, but is removed from this example cause it does not show in a tool-tip) Here:<br>

                  #. .. code:: de1

                           <font bgcolor=white color=gray>message</font> is the actual message to the ouput. Note that strformat is used.<br>

                  #. .. code:: de1

                            <font bgcolor=white color=gray>tok</font> is the name of the selected token<br>

                  #. .. code:: de2

                           <font bgcolor=white color=gray>usedMove</font> is the amount of cells the token moved<br>

                  #. .. code:: de1

                         <font bgcolor=white color=gray>limitMovement</font> is the max amount the token is allowed to move.<br>

                  #. .. code:: de1

                           These you can use to create your own message type <b>as long as the resulting output is a number</b>. E.g.:<br>

                  #. .. code:: de1

                           <font bgcolor=white color=gray>

                  #. .. code:: de1

                           [r,if(getState(&quot;Dead&quot;) &#124;&#124; getState(&quot;Incapacitated&quot;), CODE:{

                  #. .. code:: de2

                             [r:0]    

                  #. .. code:: de1

                                [h:message  = &quot;%{tok} is incapacitated and cannot move&quot;]

                  #. .. code:: de1

                         };{

                  #. .. code:: de1

                                [r:4*Dexterity]

                  #. .. code:: de1

                            }]

                  #. .. code:: de2

                         </font></html>">

                  #. .. code:: de1

                            Enter code here (hover over this for more info)

                  #. .. code:: de1

                         </html></span></html>

                  #. .. code:: de1

                        ')]

            For this to work I had to replace the quotes (") and the OR
            bars (||) by there ASCII representation. This is the result:

            |Advanced Example Tooltip.jpg|

            Note that this technique isn't perfect, because HTML tags
            inside the ``title`` may be interpreted as ending tags in
            the outer ``<html>`` block as the ``input()`` function is
            merely processing text and not looking at the content.

         | 
         | **8. Images in Input** It requires a bit of fiddling, but
           because HTML is allowed it's possible to add images to your
           input functions as well (besides the LIST trick described
           above). This can simply be done with the ``<html><img>``
           tags. However the preset image size, e.g. from
           ``getTokenHandout(90)`` which retrieves the asset ID of the
           token handout and presets it to a max width or height
           (whichever is bigger) of 90 pixels, does work for ``LABEL``
           but not for the rest! Example use:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:input("junk|<html><img src='"+getTokenHandout(90)+"'></img></html>|-|LABEL|SPAN=TRUE")]

         .. container:: template_note

            **b89 (and possibly b90)**: this will not work anymore.

         ∗

         ::

            As a workaround, use this: 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:input("junk|<html><img src='"+replace(getTokenHandout(), ":", "&#58;")+"' height=90 width=90></img></html>|-|LABEL|SPAN=TRUE")]

         |LABEL Picture.jpg|

         For other uses, e.g. choosing a picture from a ``RADIO``
         option, you will need to limit the image sizes using the image
         tags:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:me = getSelected()]

               #. .. code:: de1

                     [h, token(me),CODE:{

               #. .. code:: de1

                        [image     = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenImage()+"'></img> </td></tr><tr><td align='center'>Image</td>   </tr></table></html>"]

               #. .. code:: de1

                         [portrait    = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenPortrait()+"'></img>  </td></tr><tr><td align='center'>Portrait</td>    </tr></table></html>"]

               #. .. code:: de2

                         [handout = "<html><table><tr><td height='100'><img width=90 height=90 src='"+getTokenHandout()+"'></img>   </td></tr><tr><td align='center'>Handout</td> </tr></table></html>"]

               #. .. code:: de1

                     }] 

               #. .. code:: de1

                      

               #. .. code:: de1

                     [H: abort(input(

               #. .. code:: de1

                       "junk|<html><b>Choose picture to show to players:<br></html>|-|LABEL|SPAN=TRUE",

               #. .. code:: de2

                         "picChoice|"+image+","+portrait+","+handout+"|Which picture|RADIO|ORIENT=H SELECT=2",

               #. .. code:: de1

                       "picSize|100|Size of picture (px)"

               #. .. code:: de1

                     ))]

               #. .. code:: de1

                      

               #. .. code:: de1

                     [r,token(me), if(picChoice == 0): "<img src='"+getTokenImage(picSize)+"'></img>"]

               #. .. code:: de2

                     [r,token(me), if(picChoice == 1): "<img src='"+getTokenPortrait(picSize)+"'></img>"]

               #. .. code:: de1

                     [r,token(me), if(picChoice == 2): "<img src='"+getTokenHandout(picSize)+"'></img>"]

         |RADIO Picture.jpg|

         **9. Using PROPS**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: abort(input("resultVars|strength=0;toughness=0;willpower=0|Enter values|PROPS|SPAN=TRUE SETVARS=UNSUFFIXED"))]

               #. .. code:: de1

                     [r:resultVars]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=input&oldid=6293"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Miscellaneous
         Function </rptools/wiki/Category:Miscellaneous_Function>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=input>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/input>`__
            -  `Discussion </maptool/index.php?title=Talk:input&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/input>`__
            -  `View
               source </maptool/index.php?title=input&action=edit>`__
            -  `View
               history </maptool/index.php?title=input&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/input>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/input>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=input&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=input&oldid=6293>`__
            -  `Page
               information </maptool/index.php?title=input&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 11 June 2014, at 21:26.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |simple-input.jpg| image:: /maptool/images/e/e8/simple-input.jpg
   :width: 289px
   :height: 218px
   :target: /rptools/wiki/File:simple-input.jpg
.. |Input-checksntext.jpg| image:: /maptool/images/f/f4/Input-checksntext.jpg
   :width: 394px
   :height: 239px
   :target: /rptools/wiki/File:Input-checksntext.jpg
.. |Input-lists.jpg| image:: /maptool/images/2/21/Input-lists.jpg
   :width: 381px
   :height: 274px
   :target: /rptools/wiki/File:Input-lists.jpg
.. |Advanced Example Tooltip.jpg| image:: /maptool/images/1/12/Advanced_Example_Tooltip.jpg
   :width: 872px
   :height: 348px
   :target: /rptools/wiki/File:Advanced_Example_Tooltip.jpg
.. |LABEL Picture.jpg| image:: /maptool/images/a/a1/LABEL_Picture.jpg
   :width: 268px
   :height: 234px
   :target: /rptools/wiki/File:LABEL_Picture.jpg
.. |RADIO Picture.jpg| image:: /maptool/images/0/08/RADIO_Picture.jpg
   :width: 520px
   :height: 339px
   :target: /rptools/wiki/File:RADIO_Picture.jpg
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
