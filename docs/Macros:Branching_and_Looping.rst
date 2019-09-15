=========================================
Macros:Branching and Looping - MapToolDoc
=========================================

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

   .. rubric:: Macros:Branching and Looping
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

         .. container:: template_intermediate

            | INTERMEDIATE
            | THIS IS AN INTERMEDIATE ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Introduction <#Introduction>`__
            -  `2 Branching <#Branching>`__

               -  `2.1 IF Option <#IF_Option>`__

                  -  `2.1.1 Usage <#Usage>`__
                  -  `2.1.2 Example <#Example>`__
                  -  `2.1.3 Note <#Note>`__

               -  `2.2 SWITCH Option <#SWITCH_Option>`__

                  -  `2.2.1 Usage <#Usage_2>`__
                  -  `2.2.2 Example <#Example_2>`__

               -  `2.3 MACRO Option <#MACRO_Option>`__

                  -  `2.3.1 Usage <#Usage_3>`__
                  -  `2.3.2 Examples <#Examples>`__
                  -  `2.3.3 Location
                     Requirements <#Location_Requirements>`__
                  -  `2.3.4 Notes <#Notes>`__

               -  `2.4 TOKEN Option <#TOKEN_Option>`__

                  -  `2.4.1 Usage <#Usage_4>`__
                  -  `2.4.2 Examples <#Examples_2>`__

            -  `3 Looping <#Looping>`__

               -  `3.1 COUNT Option <#COUNT_Option>`__

                  -  `3.1.1 Usage <#Usage_5>`__
                  -  `3.1.2 Example <#Example_3>`__

               -  `3.2 FOR Option <#FOR_Option>`__

                  -  `3.2.1 Usage <#Usage_6>`__
                  -  `3.2.2 Example <#Example_4>`__

               -  `3.3 FOREACH Option <#FOREACH_Option>`__

                  -  `3.3.1 Usage <#Usage_7>`__
                  -  `3.3.2 Example Using a
                     List <#Example_Using_a_List>`__
                  -  `3.3.3 Example Using a JSON
                     Array <#Example_Using_a_JSON_Array>`__
                  -  `3.3.4 Example Using a JSON
                     Object <#Example_Using_a_JSON_Object>`__

               -  `3.4 WHILE Option <#WHILE_Option>`__

                  -  `3.4.1 Usage <#Usage_8>`__
                  -  `3.4.2 Example <#Example_5>`__

            -  `4 Code Execution <#Code_Execution>`__

               -  `4.1 CODE <#CODE>`__

                  -  `4.1.1 Usage <#Usage_9>`__
                  -  `4.1.2 Example <#Example_6>`__
                  -  `4.1.3 Nested CODE Blocks <#Nested_CODE_Blocks>`__

            -  `5 Additions <#Additions>`__

         .. rubric:: Introduction
            :name: introduction

         This page details the branching and looping structures in
         MapTool. With the exception of the block
         `if() </rptools/wiki/if>`__ statement, these are all `roll
         options </rptools/wiki/Macros:Roll:types>`__ and should follow
         the general form for roll options:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [option1[,option2]: body]

         These may be combined with other roll options (note that in
         some examples, they are combined with the `Hidden
         Roll </rptools/wiki/Macros:Roll:types#.5B_.5D_Hidden_Rolls>`__
         option (``h``) to hide the default output of the loop or
         branch).

         **If you wish to combine roll options in a single statement,
         separate the roll options with a comma, and place the colon at
         the end of the sequence of roll options. Note that some
         combinations have unpredictable results, such as
         using**\ `[if():] </rptools/wiki/if_(roll_option)>`__\ **with**\ `[macro():] </rptools/wiki/macro_(roll_option)>`__\ **.**

         For example, if you want to combine a Hidden Roll,
         `[token():] </rptools/wiki/token_(roll_option)>`__, and
         `[foreach():] </rptools/wiki/foreach_(roll_option)>`__ option
         in a single statement, you would enter the line like so:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,token("JoeRandom"),foreach(item, TokensItemList): "This item's name is "+item+"!"]

         | 

         .. rubric:: Branching
            :name: branching

         .. rubric:: IF Option
            :name: if-option

         **Introduced**: Version 1.3.b46

         This `[if():] </rptools/wiki/if_(roll_option)>`__ is a roll
         option (as mentioned above), but operates similarly to the
         block-style `if() </rptools/wiki/if>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(condition): true_body; false_body]

         or

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(condition): true_body]

         Either the ``true_body`` or ``false_body`` will be used,
         depending on the value of ``condition``. If the ``false_body``
         is not given but the ``condition`` is ``false``\ (``0``), then
         there is no output.

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:val=12]

               #. .. code-block:: none

                     [h,if(val == 12): newVal=12*12]

               #. .. code-block:: none

                     New Value = [r:newVal]

         Outputs ``New Value = 144``.

         .. rubric:: Note
            :name: note

         For an alternate method for evaluating "if" conditions, see the
         function `if() </rptools/wiki/if>`__. Note that the
         `[if():] </rptools/wiki/if_(roll_option)>`__ roll option cannot
         be (usefully) combined with the
         `[macro():] </rptools/wiki/macro_(roll_option)>`__ roll option
         as the roll options are not guaranteed to be executed in any
         particular order. This means that the
         `if() </rptools/wiki/if>`__ function is a better choice in
         those cases.

         .. rubric:: SWITCH Option
            :name: switch-option

         **Introduced**: Version 1.3.b46

         `[switch():] </rptools/wiki/switch_(roll_option)>`__ chooses
         among several options and executes code based on the switch
         expression.

         -  **Note** that the ``expression`` is a regular expression, so
            metacharacters such as ``*`` and ``()`` will need to have
            backslashes in front of them if you want to match them
            literally.

         .. rubric:: Usage
            :name: usage-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [switch(expression):

               #. .. code-block:: none

                     case case1: body1;

               #. .. code-block:: none

                     case case2: body2;

               #. .. code-block:: none

                     default: default_body]

         or with a code block:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [switch(expression), code:

               #. .. code-block:: none

                     case case1: {body1};

               #. .. code-block:: none

                     case case2: {body2};

               #. .. code-block:: none

                     default: {default_body}]

         .. rubric:: Example
            :name: example-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:powerType="at-will"]

               #. .. code-block:: none

                     [switch(powerType):

               #. .. code-block:: none

                       case "at-will": "You may use this power as much as you like";

               #. .. code-block:: none

                       case "encounter": "You may only use this power once per encounter";

               #. .. code:: de2

                       case "daily": "You may only use this power once per day"

               #. .. code-block:: none

                     ]

         Outputs ``You may use this power as much as you like``

         Using a code block:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:powerType="at-will"]

               #. .. code-block:: none

                     [switch(powerType), code:

               #. .. code-block:: none

                     case "at-will": {

               #. .. code-block:: none

                         [r:token.name]:<br>

               #. .. code:: de2

                         [r:"You may use this power as much as you like"]

               #. .. code-block:: none

                       };

               #. .. code-block:: none

                     case "encounter": {

               #. .. code-block:: none

                         [r:token.name]:<br>

               #. .. code-block:: none

                         [r:"You may only use this power once per encounter"]

               #. .. code:: de2

                       };

               #. .. code-block:: none

                     case "daily": {

               #. .. code-block:: none

                         [r:token.name]:<br>

               #. .. code-block:: none

                         [r:"You may only use this power once per day"]

               #. .. code-block:: none

                       };

               #. .. code:: de2

                     ]

         Using regex:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:powerType=".*sword.*"]

               #. .. code-block:: none

                     [switch(powerType):

               #. .. code-block:: none

                       case "flail": "one-handed weapon; two-handed does Str*2 damage";

               #. .. code-block:: none

                       case "shortsword": "used for jabs, so is a puncturing weapon";

               #. .. code:: de2

                       case "longsword": "a slashing weapon"

               #. .. code-block:: none

                     ]

         Outputs ``used for jabs, so is a puncturing weapon``. Notice
         that the first matching clause was the one that the
         `[switch():] </rptools/wiki/switch_(roll_option)>`__ option
         found.

         .. rubric:: MACRO Option
            :name: macro-option

         **Introduced**: Version 1.3.b46

         `[macro():] </rptools/wiki/macro_(roll_option)>`__ runs the
         named macro, inserting its text into chat.

         .. rubric:: Usage
            :name: usage-2

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("macro_name@location"): macro_arguments]

         The called macro sees a variable called
         ```macro.args`` </rptools/wiki/Macros:Special_Variables:macro.args>`__
         which contains the value of ``macro_arguments``. The called
         macro can set a variable called
         ```macro.return`` </rptools/wiki/Macros:Special_Variables:macro.return>`__,
         which becomes available to the calling macro. Other than
         ``macro.return``, the called macro shares no variables with the
         calling macro.

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("getDamage@Lib:combat"): damageRoll]

         Calls the macro ``getDamage`` which resides on a `library
         token </rptools/wiki/Token:library_token>`__ called
         ``Lib:combat``, and passes the variable ``damageRoll`` as an
         argument to the called macro.

         .. rubric:: Location Requirements
            :name: location-requirements

         The ``location`` can be one of the following:

         #. ``TOKEN`` - the currently impersonated token (use the word
            ``TOKEN``, not the token's name)
         #. ``Library Token`` - a `Library
            Token </rptools/wiki/Token:library_token>`__ in the current
            campaign
         #. ``this`` - if the macro is calling another macro in the same
            library, ``this`` may be used instead of retyping the full
            library token name

         .. rubric:: Notes
            :name: notes

         When a token macro calls another macro, the macro instructions
         in the *called* macro are executed against the *calling* token
         (in other words, the macro uses properties available on the
         calling token and applies all results to that token), unless
         the focus is explicitly changed to another token via either a
         roll option, or the
         `switchToken() </rptools/wiki/switchToken>`__ function, or the
         `getLibProperty() </rptools/wiki/getLibProperty>`__ function.

         Also, as of at least 1.3.b50, a variable must be given for
         ``macro_arguments``, or the *"Could not execute the command:
         Undefined function: MACRO"* error will result. However, the
         variable given as ``macro_arguments`` doesn't have to be used.

         .. rubric:: TOKEN Option
            :name: token-option

         **Introduced**: Version 1.3.b48

         `[token():] </rptools/wiki/token_(roll_option)>`__ executes a
         series of instructions against a token specified in the
         argument rather than against the token running the macro.

         This is a temporary change in the token that has the "focus" -
         only the instructions following the colon are applied to the
         designated token; following the end of that instruction block,
         operations resume being performed against the token running the
         macro.

         To permanently switch (for the duration of the macro) the token
         against which macro commands are executed, see the
         `switchToken() </rptools/wiki/switchToken>`__ function.

         .. rubric:: Usage
            :name: usage-3

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [token(token_identifier): ]

         Executes the roll against token specified by
         ``token_identifier``, which can either be the token name or
         token id.

         .. rubric:: Examples
            :name: examples-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:target="Orc 5"]

               #. .. code-block:: none

                     [h,token(target): targetAC = getProperty("AC")]

         Uses the `getProperty() </rptools/wiki/getProperty>`__ function
         to retrieve the property ``AC`` from the token named
         ``"Orc 5"``, and assigns that value to the variable
         ``targetAC``. ``targetAC`` can be used in future calculations,
         such as determining whether an attack hits. If the
         `[token():] </rptools/wiki/token_(roll_option)>`__ option was
         not used, the macro would have looked for the property ``AC``
         on the token currently *running* the macro. Note also that this
         function is considered
         `trusted </rptools/wiki/Macros:TrustedMacros>`__.

         .. rubric:: Looping
            :name: looping

         .. rubric:: COUNT Option
            :name: count-option

         **Introduced**: Version 1.3.b41

         The `[count():] </rptools/wiki/count_(roll_option)>`__ option
         executes a statement for a specified number of times, storing
         the number of the current iteration in a variable called
         ``roll.count``.

         .. rubric:: Usage
            :name: usage-4

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [count(num): body]

               #. .. code-block:: none

                     [count(num, separator): body]

         The ``roll.count`` variable will take on values from ``0`` to
         ``(number of loops - 1)``. The optional separator (default
         ``","``) is printed between each iteration.

         .. rubric:: Example
            :name: example-2

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:numHits=3]

               #. .. code-block:: none

                     [count(numHits): Damage = Damage + 1d12]

         This will iterate the ``Damage = Damage + 1d12`` operation 3
         times, separating the result of each iteration with the default
         separator (a comma). An optional second argument to
         `[count():] </rptools/wiki/count_(roll_option)>`__ allows the
         setting of a different separator.

         .. rubric:: FOR Option
            :name: for-option

         **Introduced**: Version 1.3.b46

         Executes a statement for a number of iterations based on a
         start and end value.

         .. rubric:: Usage
            :name: usage-5

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(var, start, end): body]

               #. .. code-block:: none

                     [for(var, start, end, stepsize): body]

               #. .. code-block:: none

                     [for(var, start, end, stepsize, separator): body]

         The ``var`` variable counts from ``start`` to ``1`` short of
         ``end`` during the loop (so the ``end`` number will not be part
         of the loop). The optional ``stepsize`` (default ``+1``) is
         added to ``var`` at each iteration. The loop does *not*
         evaluate when ``var`` reaches ``end``.

         .. rubric:: Example
            :name: example-3

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(i,10,0,-2): "i is now " + i]

         Counts down even numbers from 10 to 2.

         .. rubric:: FOREACH Option
            :name: foreach-option

         **Introduced**: Version 1.3.b46

         Iterates over the contents of a string list in the format
         ``"item1, item2, item3"``, the contents of a JSON Array, or the
         keys of a JSON Object.

         .. rubric:: Usage
            :name: usage-6

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [foreach(var, list): body]

               #. .. code-block:: none

                     [foreach(var, list, output_separator): body]

               #. .. code-block:: none

                     [foreach(var, list, output_separator, list_separator): body]

               #. .. code-block:: none

                     [foreach(var, jsonarray): body]

               #. .. code:: de2

                     [foreach(var, jsonarray, output_separator): body]

               #. .. code-block:: none

                     [foreach(var, jsonobject): body]

               #. .. code-block:: none

                     [foreach(var, jsonobject, output_separator): body]

         .. rubric:: Example Using a List
            :name: example-using-a-list

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: enemyList="Orcs, Goblins, Ogres, Trolls"]

               #. .. code-block:: none

                     [foreach(enemy, enemyList, "<br>"): "You really hate " + enemy]

         Outputs:

         ::

            You really hate Orcs
            You really hate Goblins
            You really hate Ogres
            You really hate Trolls

         .. rubric:: Example Using a JSON Array
            :name: example-using-a-json-array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: weapons = json.append("[]", "Longsword", "Dagger", "Bow")]

               #. .. code-block:: none

                     [foreach(wpn, weapons): wpn]

         Outputs:

         ::

            Longsword, Dagger, Bow

         .. rubric:: Example Using a JSON Object
            :name: example-using-a-json-object

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: weaponData = json.set("{}",

               #. .. code-block:: none

                         "Name": "Longsword",

               #. .. code-block:: none

                         "Damage": "1d6",

               #. .. code-block:: none

                         "Type": "Slashing",

               #. .. code:: de2

                         "Weight": 30,

               #. .. code-block:: none

                     )]

               #. .. code-block:: none

                     [foreach(field, weaponData): field]

         Outputs:

         ::

            Name, Damage, Type, Weight

         If you really wanted to see the key *and* the data, try this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: weaponData = json.set("{}",

               #. .. code-block:: none

                         "Name": "Longsword",

               #. .. code-block:: none

                         "Damage": "1d6",

               #. .. code-block:: none

                         "Type": "Slashing",

               #. .. code:: de2

                         "Weight": 30,

               #. .. code-block:: none

                     )]

               #. .. code-block:: none

                     [foreach(field, weaponData):

               #. .. code-block:: none

                         field + ": " + json.get(weaponData, field)]

         Outputs:

         ::

            Name: Longsword, Damage: 1d6, Type: Slashing, Weight: 30

         *P.S.: Note the trailing comma after the Weight field in
         the*\ `json.set() </rptools/wiki/json.set>`__\ *function? It's
         ignored. But putting it in makes it easier to copy/paste new
         lines into the function...*

         .. rubric:: WHILE Option
            :name: while-option

         **Introduced**: Version 1.3.b46

         Repeatedly executes a statement until a condition becomes
         false.

         .. rubric:: Usage
            :name: usage-7

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [while(condition): body]

               #. .. code-block:: none

                     [while(condition, separator): body]

         .. rubric:: Example
            :name: example-4

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:num=10]

               #. .. code-block:: none

                     [while(num>=0): num = num-1]

         Outputs ``9,8,7,6,5,4,3,2,1``

         .. rubric:: Code Execution
            :name: code-execution

         .. rubric:: CODE
            :name: code

         **Introduced**: Version 1.3.b46

         The `[code():] </rptools/wiki/code_(roll_option)>`__ option is
         used in conjunction with looping / branching options to execute
         multiple statements within a single "block" of a loop or
         branch, allowing the creation of more complex loops and
         branches.

         .. rubric:: Usage
            :name: usage-8

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [code: { code_block }]

         The ``code_block`` is a collection of text and macro code,
         enclosed in a single ``{}`` pair. Everything within the ``{}``
         is treated as a single block for the purposes of any looping or
         branching options.

         .. rubric:: Example
            :name: example-5

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:num=5]

               #. .. code-block:: none

                     [while(num > 0), code:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                       This is iteration [r:num] <br>

               #. .. code:: de2

                       There are [r:num-1] iterations left<br>

               #. .. code-block:: none

                       [num=num-1]

               #. .. code-block:: none

                     }]

         Outputs:

         ::

            This is iteration 5 There are 4 iterations left
            4, This is iteration 4 There are 3 iterations left
            3, This is iteration 3 There are 2 iterations left
            2, This is iteration 2 There are 1 iterations left
            1, This is iteration 1 There are 0 iterations left
            0

         **NOTE**: the digit output at the beginning of each line is an
         artifact of the
         `[while():] </rptools/wiki/while_(roll_option)>`__ loop's
         evaluation of ``num`` - since this roll does not have the
         `[h:] </rptools/wiki/h_(roll_option)>`__ option active, the
         result of that evaluation is displayed.

         .. rubric:: Nested CODE Blocks
            :name: nested-code-blocks

         To nest ``code:{}`` blocks, use a second
         `[code():] </rptools/wiki/code_(roll_option)>`__ option, like
         so:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:d20roll=1d20]

               #. .. code-block:: none

                     [h:attackRoll=d20roll+AttackBonus]

               #. .. code-block:: none

                     [h,if(attackRoll >= 16),code:

               #. .. code-block:: none

                     {

               #. .. code:: de2

                       [if(d20roll == 20),code:

               #. .. code-block:: none

                       {

               #. .. code-block:: none

                         The attack is a critical hit!

               #. .. code-block:: none

                         [h:damage=critDamage]

               #. .. code-block:: none

                       };

               #. .. code:: de2

                       {

               #. .. code-block:: none

                         The attack is a hit!

               #. .. code-block:: none

                         [h:damage=regDamage]

               #. .. code-block:: none

                       }]

               #. .. code-block:: none

                     };

               #. .. code:: de2

                     {

               #. .. code-block:: none

                       The attack misses!

               #. .. code-block:: none

                     }]

         MapTool can only handle two levels of nested code.

         .. rubric:: Additions
            :name: additions

         Conditional Operators:

         -  ``>`` - Greater than
         -  ``<`` - Less than
         -  ``>=`` - Greater than or equal to
         -  ``<=`` - Less than or equal to
         -  ``==`` - Equal to
         -  ``!=`` - Not equal

         Logical Operators:

         -  ``&&`` - And
         -  ``¦¦`` - Or

         It is important to note that the *Equal* condition operator
         must be two equal signs. If you are checking for a text string,
         place quotes around the text.

         Operator Precedence:

         -  ``( )`` - Parentheses are always done first; they can be
            nested
         -  ``!`` - Logical NOT
         -  ``&&`` - Logical AND
         -  ``¦¦`` - Logical OR

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Macros:Branching_and_Looping&oldid=7034"

