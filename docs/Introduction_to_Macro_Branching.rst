============================================
Introduction to Macro Branching - MapToolDoc
============================================

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

   .. rubric:: Introduction to Macro Branching
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
            -  `2 Assumptions <#Assumptions>`__
            -  `3 New Concept: Roll
               Options <#New_Concept:_Roll_Options>`__
            -  `4 New Concept: The CODE
               Option <#New_Concept:_The_CODE_Option>`__
            -  `5 New Concept: Comparison and Logical
               Operators <#New_Concept:_Comparison_and_Logical_Operators>`__

               -  `5.1 Comparisons <#Comparisons>`__
               -  `5.2 Logical <#Logical>`__

            -  `6 IF: Comparing Values <#IF:_Comparing_Values>`__

               -  `6.1 if() Function <#if.28.29_Function>`__
               -  `6.2 [if():] Roll
                  Option <#.5Bif.28.29:.5D_Roll_Option>`__
               -  `6.3 IF and CODE <#IF_and_CODE>`__

            -  `7 SWITCH: Choosing from Many
               Options <#SWITCH:_Choosing_from_Many_Options>`__

               -  `7.1 SWITCH and CODE <#SWITCH_and_CODE>`__

            -  `8 Advanced Branching
               Options <#Advanced_Branching_Options>`__

         .. rubric:: Introduction
            :name: introduction

         When you write a macro, you'll frequently find yourelf wanting
         to either repeat an operation several times, or to choose from
         several options based on the outcome of a macro command. In
         game terms, you might want to make an damage roll several times
         in a row (say, one time for each enemy caught by a grenade
         blast), or you might want your macro to give you a damage roll
         *if* you hit, and say ``You missed!`` if you miss.

         In programming jargon, those concepts are called *looping*
         (where you go through a process repeatedly, or "loop through
         it"), and *branching* (where your program - in this case, the
         macro - "branches" down different paths). The MapTool macro
         language has several roll options (and one function) to let you
         branch and/or loop your commands.

         Finally, because there are a lot of times when you'll want to
         do *several* things at the same time when you branch or loop,
         there's a special roll option called *code* that tells MapTool
         to treat several macro commands as a single "unit" when you
         loop or branch. That may sound confusing, but you'll see what
         it all means shortly!

         Since there's a lot of ground to cover, this tutorial will
         cover *branching* (running different commands based on some
         condition). The `Introduction to Macro
         Loops <Introduction_to_Macro_Loops>`__ will
         handle looping (running a process repeatedly, until you wish it
         to stop).

         .. rubric:: Assumptions
            :name: assumptions

         We're going to get to using these options pretty fast, so I
         assume you've read the `Introduction to Macro
         Writing <Introduction_to_Macro_Writing>`__ and
         have knowledge of how to create a new macro and use some very
         basic commands in it (like creating a variable or a dice roll).

         There are a couple concepts that should be introduced first,
         since they're going to be a great way to illustrate some of the
         branching concepts (and looping concepts, in the `Introduction
         to Macro Loops <Introduction_to_Macro_Loops>`__.
         You'll get an explanation of the new concepts below.

         Also, don't forget to enable the *Use ToolTips for Inline
         Rolls* option in MapTool Preferences.

         .. rubric:: New Concept: Roll Options
            :name: new-concept-roll-options

         MapTool's macro language presents the user the ability to use
         both named functions - things with names like
         {code|getProperty()} or {code|nextInitiative()}, and Roll
         Options, which are not functions but instead special commands
         that are placed at beginning of a line of macro script. Roll
         Options are effectively "switches" or "toggles" that you set
         for a macro command that affect how MapTool will handle the
         commands contained within the line of macro code. A couple
         simple roll options are mentioned in the Introduction to Macro
         Writing - things like [h:] and [e:] for hidden or expanded
         output, for example. However, there are more complex ones, and
         to use branching and looping, you'll need to be familiar with
         them.

         Roll options must follow these rules:

         #. Appear at the beginning of a macro command
         #. If only one roll option is on the line, it ends with a
            colon. For example: [h:]
         #. If multiple roll option are on the same command, they are
            separated by commas, and the last one is followed by a
            colon. For example, [h,if(HP > 0): command]
         #. If a roll option takes an argument - that is, it has
            parentheses and wants you to put something in them, like a
            comparison - the colon (or comma, if there are multiple roll
            options) goes after the parentheses.

         .. rubric:: New Concept: The CODE Option
            :name: new-concept-the-code-option

         Normally, in any branching or looping technique, MapTool lets
         you do *one thing* - that is, one command. So if you had a
         statement that said "if a condition is true, do something
         cool," then "something cool" can only be one single thing - you
         might roll some dice, or assign a variable, or print out some
         text to the chat window. However, you couldn't roll some dice,
         assign a variable, assign *another* variable, do some math, and
         *then* print out something all in that statement. That's too
         many operations.

         If you could only do one thing when you branch or loop, macros
         would be very limited - so the macro language supports a
         special roll option called
         `[code():] <code_(roll_option)>`__, which
         indicates to MapTool that you want to perform several different
         operations at once, but have them all be treated as a single
         unit (a single "branch" of a branching statement, or the body
         of the loop in a looping option). You would group these several
         commands inside a pair of curly braces ( { } ).

         The examples below will use the
         `[code():] <code_(roll_option)>`__ option, so you
         can see how it works.

         .. rubric:: New Concept: Comparison and Logical Operators
            :name: new-concept-comparison-and-logical-operators

         In macro writing, you're going to want to compare values
         together a lot - is my dice roll greater than 20? Are my hit
         points less than 0? Does that weapon name equal "Warhammer?"
         All of these are handled via comparison operators and logical
         operators.

         *Comparison Operator* is programming jargon for the symbols we
         use to have MapTool compare two values to each other in certain
         ways (an *operator* is a symbol that performs an operation -
         for instance, the + symbol is an operator that adds things
         together).

         A *Logical Operator* is a symbol you use to instruct MapTool in
         what order to consider comparisons, and how to group
         comparisons together. The comparison and logical operators are
         described below:

         In the examples below, the `if() <if>`__ function
         is used to illustrate the examples. It's described in more
         detail later, but the basic "format" of the
         `if() <if>`__ function is this:

         ``if(comparison, value_if_true, value_if_false)``

         -  **Comparison** is where you do your actual comparison
            (greater than, less than, etc.)
         -  **Value_if_true** is where you put the output or value if
            the comparison is true
         -  **Value_if_false** is, obviously, where you put the output
            or value if the comparison is false

         .. rubric:: Comparisons
            :name: comparisons

         The symbols below are the comparison operators. Remember that
         you must always think of these comparisons from the reference
         point of the value on the *left* side. So, in the comparison
         ``value1 > value2``, you read it based on the left side: "is
         ``value1`` greater than ``value2``. This is the rule for
         comparisons in MapTool - the left side of the operator is the
         "point of view."

         -  **==**: "is equal to;" this is the operator you use to see
            if one value is equal to another. Be careful - it has *two*
            equals signs in a row (remember, one equal sign is already
            reserved for assigning values to variable). An example of
            this comparison would look like
            ``[if(hit == "yes", "you hit!", "you missed!")]``
         -  **>**: "is greater than; use this to see if the value on the
            left side is greater than the value on the right. For
            example: {{code|[if(roll > 17, "Hit!", "Miss")]. You can put
            a number on the left side, like
            ``[if(17 > roll, "Miss", "Hit!")]`` (note that it basically
            reverses the first example, so you need to switch the true
            and false outputs).
         -  **>=**: "is greater than or equal to"; use this to see if
            the value on the left side is greater than *or equal to* the
            value on the right. For example:
            ``[if(roll >= 17, "Hit!", "Miss")]``
         -  **<**: "is less than"; use this to see if the value on the
            left side is *less than* the value on the right. For
            example, ``[if(roll < 19, "Miss", "Hit!")]``}
         -  **<=**: "is less than or equal to"; use this to see if the
            value on the left side is *less than or equal to* the value
            on the right. For example:
            ``[if(roll <= 18, "normal hit", "critical hit")]``
         -   !=: "is not equal to"; use this to compare whether the
            value on the left side is *not equal to* the value on the
            right. Note that this operator doesn't care what the values
            actually *are*, only that they are *not equal*. For example,
            ``{{{1}}}``

         .. rubric:: Logical
            :name: logical

         The symbols below are the *logical operators*. You use this to
         group comparisons together (you only need these if you need to
         make multiple comparisons at the same time). These go *between*
         individual comparisons (these don't replace the comparison
         operators above!).

         -  **&&**: "and"; use this if you want to make sure that two or
            more comparisons are *all* true. For example:
            ``[if(roll > 1 && roll < 20, "Hit", "Miss")]`` requires
            *both* comparisons to be true, for the whole comparison
            group to be true. In other words, the roll must be *greater
            than 1* **and** *less than 20* in order for it to be a hit.
            If both of those aren't true, the output is ``Miss``.

            -  **Remember: if you use &&, every part of the comparison
               statement must be true for the whole comparison to be
               true!**

         -  **\|\|**: "or"; use this if you want or need only one out of
            multiple comparisons to be true, in order for the whole
            thing to be true. For example, ````. In the example, if
            *either* condition is true (that is, if ``enemyHealth`` is
            "dead" *or* "dying") the entire comparison group is true.
            Only if *neither* comparison is true does the whole thing
            become false.

            -  **Remember: use \|\| if you only need one out of several
               comparisons to be true**

         .. rubric:: IF: Comparing Values
            :name: if-comparing-values

         One of the most elementary ways to branch any code is the use
         of the idea of *if - then*. That is, *if* some comparison is
         true, *then* do something else. You would use the *if* concept
         to say "If my attack hits, then show the damage result!"

         MapTool's macro language has two kinds of if - a function (a
         function is a pre-defined set of instructions that you can
         "call" by referring to it by name), and a roll option (a roll
         option is a "switch" or "toggle" that tells MapTool how to
         handle a command.

         .. rubric:: if() Function
            :name: if-function

         The `if() <if>`__ function is called simply by
         writing ``if()`` and putting the thing you want compared, what
         to do if the comparison is true, and what to do if the
         comparison is false, all inside the parentheses. The general
         format is:

            ``if(comparison, value_if_true, value_if_false)``

         An actual example would look like:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [if(attackHits == "yes", "You hit!", "You missed")]

         In that single line, we've said:

         -  Check the variable ``attackHits`` to see if it has the value
            "yes"
         -  If it has the value "yes", then print ``You hit!`` to chat,
            or
         -  If it does *not* have the value "yes", then prin
            ``You missed`` to chat

         The *value_if_true* and *value_if_false* parts of the
         `if() <if>`__ statement can be text, dice roll
         commands (like 1d6 or 1d20), or variables. What they *cannot*
         be is variable assignments - that is, you can't write an
         `if() <if>`__ statement like this:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [if(attackHits=="yes", output = "You Hit!", output = "You missed")]

         It may seem like a good idea, but it won't work - MapTool will
         give what's known as a *null pointer exception*, and the macro
         will fail. However, there is a trick to get around that: since
         `if() <if>`__ is a function, and all functions -
         when they run - produce a *value*, you can assign the *result*
         of it to a variable! You would do it like this:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [output = if(attackHits=="yes", "You Hit!", "You missed")]

         When you do it that way, MapTool will:

         -  First, decide what the result of the
            `if() <if>`__ is, and
         -  Second, assign that *result* to the variable ``output``,
            which you can then use like any variable

         .. rubric:: `[if():] <if_(roll_option)>`__\ Roll
            Option
            :name: if-roll-option

         In addition to `if() <if>`__, there is another
         way to employ the concept of "if-then" in macro code. The
         `[if():] <if_(roll_option)>`__ *roll option*.
         Roll options are, as mentioned above, effectively "switches" or
         "toggles" that you set for a macro command that affect how
         MapTool will handle it. A couple simple roll options are
         mentioned in the `Introduction to Macro
         Writing <Introduction_to_Macro_Writing>`__ -
         things like `[h:] <h_(roll_option)>`__ and
         `[e:] <e_(roll_option)>`__ for hidden or expanded
         output, for example.

         Roll options must follow these rules:

         #. Appear at the beginning of a macro command
         #. If only **one** roll option is on the line, it ends with a
            colon. For example: ``[h:]``
         #. If *multiple* roll option are on the same command, they are
            separated by commas, and the *last* one is followed by a
            colon. For example, ``[h,if(HP > 0): command]``
         #. If a roll option takes an *argument* - that is, it has
            parentheses and wants you to put something in them, like a
            comparison - the colon (or comma, if there are multiple roll
            options) goes *after* the parentheses. Look at the examples
            below to see how it's used.

         To use the `[if():] <if_(roll_option)>`__ option
         as a comparison, you must follow the format:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [if(comparison): command_if_true; command_if_false]

         | 

         -  **Comparison**: this is a comparison statement, as used in
            the `if() <if>`__ above.
         -  **Command_if_true**: this is the command to execute if true;
            in this form of IF, you *can* do variable assignments or
            commands that you cannot do in the
            `if() <if>`__ method. However, it doesn't
            *have* to be a whole command - it can still be a bit of
            text.
         -  **Command_if_false**: this is the command to execute if
            false. This is an optional statement - if you want it to do
            nothing if the comparison is false, then leave off the
            semicolon and the ``command_if_false`` part entirely.

         An example of the use of the
         `[if():] <if_(roll_option)>`__ roll option might
         be:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h,if(attackHits == "yes"): output="You hit!"; output="You missed"]
                     Result of your attack: [r:output]

         In the above example, the following things are happening:

         -  MapTool compares the value of ``attackHits`` to the value
            ``"yes"``

            -  If the comparison is *true* - that is, the value of
               ``attackHits`` is *indeed* equal to ``"yes"`` - it
               assigns the value ``"You hit!"`` to the variable
               ``output``.
            -  If the comparison is *false* - the value of
               ``attackHits`` is *not equal to* ``"yes"`` - it assigns
               the value ``"You missed"`` to the variable ``output``.

         -  It then prints a short line of text and the value of
            ``output`` to chat.

         You'll note that the first line - the line that uses if - has
         **two** roll options on the same line:
         `[h:] <h_(roll_option)>`__ and
         `[if():] <if_(roll_option)>`__. You'll also see
         that they are separated by a comma, and the colon goes *after*
         the last roll option, and *before* the commands in the
         ``command_if_true`` and ``command_if_false`` sections.

         .. rubric:: IF and CODE
            :name: if-and-code

         So what if you want to do more than one thing based on a
         comparison? Say, set a bunch of variables to a certain value?
         For that, you use the
         `[code():] <code_(roll_option)>`__ roll option.

         Like all roll options,
         `[code():] <code_(roll_option)>`__ is put at the
         beginning of the line, separated from other roll options by a
         comma. Macro programming convention (that is, the way most
         macro writers seem to do it) is to put
         `[code():] <code_(roll_option)>`__ as the last
         roll option in the list. So, the general format you will see in
         a macro is likely to be:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [roll_option1, roll_option2, code: macro_commands]

         The second component of the
         `[code():] <code_(roll_option)>`__ option is the
         curly bracket ({ }). You use these to enclose multiple commands
         as a single group. Remember the format of the
         `[if():] <if_(roll_option)>`__ roll option?

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [if(comparison): command_if_true; command_if_false]

         Well, the `[code():] <code_(roll_option)>`__
         option lets you replace ``command_if_true`` and
         ``command_if_false`` with *multiple* macro commands. Let's look
         at an example:

         Suppose we write a macro to look at a variable called
         ``attackRoll``. We want to compare it to a number (the target
         number), which is held by the variable ``targetNumber``. Here's
         what we want the macro to do:

         If ``attackRoll`` is greater than or equal to ``targetNumber``,
         the macro should:

         -  Set ``attackUsed`` to "yes"
         -  Set ``attackResult`` to "hits"
         -  Set ``attackRecharge`` to 3
         -  Set ``damageRoll`` to the result of the dice roll 1d8+4.
         -  Output a string telling the user the results.

         If ``attackRoll`` is *not* greater than or equal to
         ``targetNumber``, the macro should:

         -  Set ``attackUsed`` to "Yes"
         -  Set ``attackResult`` to "misses"
         -  Set ``attackRecharge`` to 3
         -  Set ``damageRoll`` to "no"
         -  Output a string to chat telling the user the results.

         Here's how to do it:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:attackRoll = 1d20]
                     [h:targetNumber = 15]
                      
                     [h,if(attackRoll >= targetNumber), code:
                     {
                       [attackUsed = "yes"]
                       [attackResult = "hits"]
                       [attackRecharge = 3]
                       [damageRoll = 1d8+4]
                     };
                     {
                       [attackUsed = "yes"]
                       [attackResult = "misses"]
                       [attackRecharge = 3]
                       [damageRoll = "no"]
                     }]
                      
                     Your attack [attackResult], and you do [damageRoll] damage. Your attack will recharge in [attackRecharge] rounds.

         There's a lot going on here, but the important thing to look
         for is the CODE option in the very first line, and the curly
         braces. The curly braces enclose multiple separate commands,
         but say to MapTool, "treat these as one thing". So in the
         example above:

         -  We declare two variables, ``attackRoll`` and
            ``targetNumber``, and give them initial values (in this
            case, ``attackRoll`` will be the result of a 1d20 roll, and
            ``targetNumber`` is set to 15).
         -  We set up the comparison (putting an h, in front - remember,
            that will hide the results from chat, so you don't see all
            the calculations in the if statement).
         -  We put `[code():] <code_(roll_option)>`__ in
            there to warn MapTool that each part of the
            `[if():] <if_(roll_option)>`__ roll option -
            ``command_if_true`` and ``command_if_false`` - will actually
            consist of multiple separate commands.
         -  We put a colon after the word ``code``, to mark off the end
            of all the roll options. There is only ONE colon in the
            line!
         -  We use a { to mark the start of the ``command_if_true``
            portion of the IF statement. We then put in our commands,
            each one separately and enclosed in square brackets. Once
            finished, we *close* that section of the IF statement with a
            }, and put a semicolon on the end (remember, the IF roll
            option needs a semicolon to separate ``command_if_true``
            from ``command_if_false``.
         -  We do the same process for the ``command_if_false`` section
            - a { followed by a series of commands, and then closed with
            a }.
         -  We make sure to close off the **whole** if statement with
            another square bracket ( ] ). Remember, an IF roll option is
            still just a macro command, and all macro commands must be
            enclosed in **[ ]**.
         -  Finally, we write some text, with the several variables we
            have inserted at appropriate points, to be sent to chat when
            the macro runs.

         | 
         | **NOTE**: The CODE roll option only works with *other roll
           options*. You would not use this with the
           `if() <if>`__ *function*. That is a bit
           confusing, but just remember: CODE only goes with other roll
           options.

         .. rubric:: SWITCH: Choosing from Many Options
            :name: switch-choosing-from-many-options

         The `if() <if>`__ function and the
         `[if():] <if_(roll_option)>`__ roll option both
         let you pick from two options - either do something when the
         comparison is *true*, or do something different when the
         comparison is *false*. But life - and RPG's - are not always so
         black and white. When you want to do different things based on
         one of *many* options, you use the
         `[switch():] <switch_(roll_option)>`__ roll
         option.

         The general format is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [switch(val):
                     case case_value1: command_1;
                     case case_value2: command_2;
                     case case_value3: command_3;
                     default: command_Default]

         What's happening here is this:

         -  MapTool is looking at the value of the variable ``val``
         -  MapTool then looks at each of the ``case`` statements in the
            switch, and compares ``val`` to ``case_value1``,
            ``case_value2``, and ``case_value3``
         -  When MapTool finds a match - that is, ``val`` is equal to
            one of those cases, the appropriate command (either
            ``command_1``, ``command_2``, or ``command_3``) is executed,
            and then MapTool exits the switch statement (which just
            means, once it's found a match, it does what that case says,
            and then stops checking for matches).

         Suppose, for example, that the we wanted a macro that would
         automatically assign the right ``Armor`` value to a token,
         based on the token's ``Class``. If you've been following along,
         you might recognize the **Armor** value as one of the
         attributes in the `Sample
         Ruleset <Sample_Ruleset>`__. If you visit the
         `Sample Ruleset <Sample_Ruleset>`__ page, you'll
         see that a character can have one of several armor values,
         based on the character's class:

         -  A **Warrior** has an armor value of 6
         -  A **Rogue** has an armor value of 2
         -  A **Wizard** has an armor value of 1
         -  A **Priest** has an armor value of 4

         So, let's say we want a macro to ask us for the value of the
         variable ``class``, and then use that variable to assign the
         right ``Armor`` value. Here's how we'd do it:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:class = "Rogue"]
                      
                     [h,switch(class):
                     case "Warrior": Armor = 6;
                     case "Rogue": Armor = 2;
                     case "Wizard": Armor = 1;
                     case "Priest": Armor = 4;
                     default: Armor = 0]
                      
                     Your Armor Value is [Armor].

         What the above example does is:

         -  Look at the value for ``class`` - if you try this out, it
            will always show the value for "Rogue." If you alter the
            ``[h:class="Rogue"]`` line, you can see how changing that
            value affects the switch statement).
         -  Compare what you put in there with the four different cases
            - checking to see if ``class`` is equal to ``"Warrior"``,
            ``"Rogue"``, ``"Wizard"``, or ``"Priest"``.
         -  If ``class`` equals any of those (and we mean EXACTLY equals
            - case sensitive, no spaces, an *exact* match), run the
            command to set the variable ``Armor`` to the appropriate
            value.
         -  If no match is found, do whatever follows the ``default``
            option (in other words, set ``Armor`` to 0.
         -  Stop looking for matches, and move on.

         .. rubric:: SWITCH and CODE
            :name: switch-and-code

         The `[code():] <code_(roll_option)>`__ option can
         be used with a
         `[switch():] <switch_(roll_option)>`__ option, in
         a similar manner as
         `[if():] <if_(roll_option)>`__. There are a
         couple tricky bits, but if you follow the pattern given in the
         examples, it should work for you.

         To do a `[switch():] <switch_(roll_option)>`__
         option with `[code():] <code_(roll_option)>`__,
         the general format is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [switch(val),code:
                     case case_1: { commands_for_case_1};
                     case case_2: { commands_for_case_2};
                     case case_3: { commands_for_case_3};
                     default: { commands_for_default}]

         An actual example can be drawn from the `Sample
         Ruleset <Sample_Ruleset>`__ as well. Not only
         does a character's class indicate his or her armor value, but
         also the list of "Beginning Powers" from which the character
         can draw. Suppose we wanted to set not only the armor value,
         but also a variable called ``beginningPowers``. To do that,
         you'd write a SWITCH that looks like:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h,switch(class),code:
                     case "Warrior":
                     {
                       [Armor = 6]
                       [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]
                     };
                     case "Rogue":
                     {
                       [Armor = 2]
                       [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]
                     };
                     case "Wizard":
                     {
                       [Armor = 1]
                       [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]
                     };
                     case "Priest":
                     {
                       [Armor = 4]
                       [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]
                     };
                     default:
                     {
                       [Armor = 0]
                       [beginningPowers = "Fists, Feet"]
                     }]
                      
                     Your Armor Value is [Armor] and your beginning powers are [beginningPowers].

         As you can see, each different case is treated as a single
         block of operations - so you need to put curly braces for each
         separate case, and separate them all with the semicolon. At the
         very end, we put a closing square bracket (**]**), to finish
         the whole command. Again, what has happened is that the CODE
         option and the curly braces have allowed you to replace a
         single command, like ``command_for_case_1``, with a *group* of
         commands.

         Also, you'll see that I've added in some line breaks so that
         each separate group of operations is easier to read - MapTool
         is cool with that, because extra line breaks *inside* a command
         (remember, commands are enclosed within **[ ]**) are ignored.
         This is nice, because it makes the macros *much* easier to
         read.

         .. rubric:: Advanced Branching Options
            :name: advanced-branching-options

         The two options illustrated above are the most common branching
         options used in macro writing. However, they are not the *only*
         options for branching macros - there are two others, which
         involve either leaving one macro entirely to call on another,
         or changing the focus (that is, what token is the `Current
         Token <Current_Token>`__) of a macro temporarily.
         Since these are fairly complex operations all on their own,
         you'll find them in the `More Branching
         Options <More_Branching_Options>`__ guide.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Macro_Branching&oldid=5697"

