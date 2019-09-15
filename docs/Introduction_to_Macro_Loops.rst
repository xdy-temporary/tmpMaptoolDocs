========================================
Introduction to Macro Loops - MapToolDoc
========================================

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

   .. rubric:: Introduction to Macro Loops
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
            -  `3 New Concept: String Lists and String
               Properties <#New_Concept:_String_Lists_and_String_Properties>`__

               -  `3.1 String Lists <#String_Lists>`__
               -  `3.2 String Properties <#String_Properties>`__

            -  `4 COUNT: Over and Over and Over
               and... <#COUNT:_Over_and_Over_and_Over_and...>`__

               -  `4.1 Special Variable:
                  roll.count <#Special_Variable:_roll.count>`__

            -  `5 WHILE: Keep On Keepin'
               On <#WHILE:_Keep_On_Keepin.27_On>`__

               -  `5.1 Example 1: Basic
                  Countdown <#Example_1:_Basic_Countdown>`__
               -  `5.2 Example 2: The
                  Machine-Gun <#Example_2:_The_Machine-Gun>`__

            -  `6 FOR: I Couldn't Think of Anything
               Catchy <#FOR:_I_Couldn.27t_Think_of_Anything_Catchy>`__

               -  `6.1 Example 1: Basic
                  Countdown <#Example_1:_Basic_Countdown_2>`__
               -  `6.2 Example 2: Creating a Table With Multiple
                  Rows <#Example_2:_Creating_a_Table_With_Multiple_Rows>`__

            -  `7 FOREACH: A Very Special
               FOR <#FOREACH:_A_Very_Special_FOR>`__

               -  `7.1 Example 1: Listing the Contents of a String
                  List <#Example_1:_Listing_the_Contents_of_a_String_List>`__
               -  `7.2 Example 2: Attacking a Bunch of Bad
                  Guys <#Example_2:_Attacking_a_Bunch_of_Bad_Guys>`__

            -  `8 Conclusion <#Conclusion>`__

         .. rubric:: Introduction
            :name: introduction

         We've looked at
         `branching <Introduction_to_Macro_Branching>`__
         in macros, using `[if():] <if_(roll_option)>`__,
         `[switch():] <switch_(roll_option)>`__, and the
         more advanced roll options
         `[macro():] <macro_(roll_option)>`__ and
         `[token():] <token_(roll_option)>`__. Branching
         is one of the most important tools for macro writing, since it
         lets you automate decisions based on certain factors or
         conditions that arise during play.

         Another common task in MapTool macros is to repeat a process
         multiple times - for example, you may want to repeat an attack
         roll several times, against multiple targets (for instance, if
         you threw a grenade, you might need to roll to see which
         targets are hit by the blast), or you may want to go through a
         list of skills, and print out the skill rating for each one. In
         both cases, you're repeating the same operation several times
         in a row, generating different results each time. In macro
         writing, we call this process *looping* (you may see it
         described in places as "looping through a list" or "iterating
         over an array" - regardless, the processes to do it are
         *loops*).

         There are four loop structures in MapTool macros:
         `[count():] <count_(roll_option)>`__,
         `[while():] <while_(roll_option)>`__,
         `[for():] <for_(roll_option)>`__, and
         `[foreach():] <foreach_(roll_option)>`__. Each of
         the three is a *roll option*, which means - as we've seen
         before:

         #. It is placed at the beginning of a macro command
         #. It is followed by a colon

            #. If more than one roll option is used, they are separated
               by commas, and the *last* one is followed by a colon

         #. After the colon, you place the operation you want to do
            every time the loop runs

         Before we continue, we'll need to introduce a couple concepts
         that will be used heavily in the examples below, especially for
         `[for():] <for_(roll_option)>`__ and
         `[foreach():] <foreach_(roll_option)>`__ loops.

         .. rubric:: Assumptions
            :name: assumptions

         I assume you've read the `Introduction to Macro
         Writing <Introduction_to_Macro_Writing>`__ and
         have knowledge of how to create a new macro and use some very
         basic commands in it (like creating a variable or a dice roll).

         Also, don't forget to enable the *Use ToolTips for Inline
         Rolls* option in MapTool Preferences.

         .. rubric:: New Concept: String Lists and String Properties
            :name: new-concept-string-lists-and-string-properties

         RPGs have a lot of information that goes into playing them -
         there are stats, and skills, and dice rolls, and weapons, and
         equipment, and powers and magic and...well, you name it, and
         there's an RPG out there that covers it.

         For basic things, it might make sense to create a token
         property for each piece of information. In fact, you can do
         this for every possible bit of information you want to record
         about a character - but already, I bet you're thinking "that's
         a *lot* of properties"). And it is!

         Fortunately, there are other ways to store information in
         MapTool properties (and macro variables) that let you group
         information together. The two new information storing methods
         we'll use - which are properly referred to as *data types* -
         are `string lists <String_List>`__ and `string
         properties <String_Property_List>`__.

         .. rubric:: String Lists
            :name: string-lists

         A string list is, first, a *string* - that is, a collection of
         alphanumeric text that is treated as just text (that is, it's
         not a number, so you can't add it to another number; it's not a
         dice roll, so MapTool won't automatically roll it; it's just a
         string of characters).

         Second, it is a *list* - a collection of single items,
         separated by some sort of separating character - the (you
         guessed it) *separator* (also called a *delimiter*). The
         separator marks the beginning and end of an individual item in
         a list. This is a long way of saying "a string list is a single
         value that is a list of things, like colors: blue, green, red,
         orange, mauve."

         Formally - in macro code - a string list looks like:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:listOfColors = "blue, green, red, orange, mauve"]

         In the example, you'll see that we've made a variable
         assignment, and given the variable ``listOfColors`` the values
         ``blue, green, red, orange, mauve``. The whole thing is
         enclosed in double quotes, which tells MapTool that it's a
         string, and from its very format, MapTool knows that it's a
         *string list*.

         A string list can contain anything - it could be a list of
         names, of numbers, of dice rolls - anything you might want to
         keep a list of.

         **However!** It is important to remember that no matter what
         each item in a string list *is*, it is always treated as a
         *string*. So if MapTool reads a string list that looks like
         ``"1d6, 2d8, 1d20"``, it will not see the first item and see a
         command to roll 1 six-sided die; instead it will see the
         character "1", the character "d", and the character "6", all
         put together. They may look the same to us, but they don't look
         the same to MapTool - to turn that "1d6" into ``1d6`` so that
         MapTool will roll it, we need to use the
         `eval() <eval>`__ function to tell MapTool
         "evaluate that string *as if* it were a dice roll." You'll see
         some examples of `eval() <eval>`__ later on.

         .. rubric:: String Properties
            :name: string-properties

         String properties are very similar to string lists - they are
         strings with special formatting, and they contain a collection
         of items. However, string properties have additional features
         that make them very useful for storing information in a
         different way.

         The essence of a string property is the the *key - value*
         pairing. Basically, for each item in the string property, there
         is a *key* that is paired with a *value*. For instance, if you
         have a weapon with the following details:

         -  Weapon Name: Broadsword
         -  Weapon Damage Dice: 1d8
         -  Weapon Damage Type: Slashing
         -  Weapon Category: Versatile

         You have a series of *key - value* pairs: the key "Weapon Name"
         is paired with the value "Broadsword," the key "Weapon Damage
         Dice" is paired with the value "1d8," and so on. A string
         property is simply a "formal" way to set up this kind of
         pairing in a single variable. The string property for the above
         weapon might read:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:weapon1 = "name=Broadsword; damageDice=1d8; damageType=Slashing; category=Versatile;"]

         In that string property, the word to the left of the equal sign
         is the *key*, and the word to the right is the *value*. The
         semicolon is the *separator* or *delimiter*. MapTool has
         special functions to retrieve and change the values within a
         string property, which you'll see in use later.

         Now, let's get to the loops!

         .. rubric:: COUNT: Over and Over and Over and...
            :name: count-over-and-over-and-over-and...

         The first looping structure we'll cover is the
         `[count():] <count_(roll_option)>`__ option. This
         option is the simplest loop - it repeats the operation
         following the colon a number of times equal to its *argument*
         (remember, arguments are the values or variables you put inside
         the parentheses). The format of a
         `[count():] <count_(roll_option)>`__ (which can
         also be abbreviated `[c():] <c_(roll_option)>`__
         statement is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [count(repetitions): command]

         or

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [c(repetitions): command]

         The example should be pretty self-explanatory. It contains:

         -  The `[count():] <count_(roll_option)>`__
            option itself - without the option, we wouldn't need this
            tutorial, right?
         -  ``repetitions``: this is the value that tells
            `[count():] <count_(roll_option)>`__ how many
            times to repeat ``command``
         -  ``command``: this is the actual macro command you want count
            to do over and over again.

         Let's look at an example. Suppose you have a character who can
         cast a spell, which creates a cloud of poisonous gas that can
         hit up to nine targets at the same time. Suppose we also have a
         cluster of 6 hapless orcs standing in the room, that you are
         about to poison with this toxic cloud. The rules of your game
         indicate that you must roll a separate attack for each possible
         target, meaning that you'd have to roll your attack 6 different
         times. You can either do that by hand, each time, or you could
         write a macro that uses
         `[count():] <count_(roll_option)>`__ to roll the
         attack over and over, and all you need to give it is the number
         of times!

         Here's how you'd write that macro:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:attackBonus = 7]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        Toxic Cloud: [count(numAttacks): 1d20+attackBonus]

         What we did here was:

         -  Line 1 sets a value for ``attackBonus``, to be used later.
         -  Line 3 sends the text "Toxic Cloud: " to chat, and then,
            begins the Count Loop. Since ``numAttacks`` is *undeclared*,
            MapTool will prompt you for a value before it can start the
            loop. Once you enter that value, the count loop will process
            the calculation of ``1d20+attackBonus`` that many times,
            sending the result to chat each time, and separating each
            result with a comma.

         The output of this macro will look something like (assuming you
         entered 4 when prompted for ``numAttacks``):

            Toxic Cloud: 17, 19, 12, 8

         .. rubric:: Special Variable: roll.count
            :name: special-variable-roll.count

         Since it's often useful to know what "round" or "turn" we're on
         when a `[count():] <count_(roll_option)>`__ loop
         is running, MapTool creates a special variable every time you
         start a count loop. This variable is called
         ```roll.count`` <roll.count>`__, and it's value
         is equal to whatever loop you're currently on. So, if you're on
         the first loop, ``roll.count`` is equal to 1; on the second
         time through, it's equal to 2, and so on. That way, you can use
         that value in various ways *inside* your macro command.

         A more advanced example of the Toxic Cloud macro might look
         like this:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:attackBonus = 7]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        Toxic Cloud vs:<br>

                  #. .. code-block:: none

                         

                  #. .. code:: de2

                        [c(numAttacks, "<br>"),CODE:

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                           [attack = 1d20+attackBonus]

                  #. .. code-block:: none

                           [damage = 1d6 + 2]

                  #. .. code-block:: none

                           Target [r:roll.count]: Attack [r:attack]; [damage] damage.

                  #. .. code:: de2

                        }]

         A bit more is going on here.

         -  Line 1 still just sets ``attackBonus`` to 7, so we can use
            it later.
         -  Line 3 outputs "Toxic Cloud vs:
            " to chat (the <br> part sends a line break to chat, meaning
            that the next output will start on the line *below* the
            words "Toxic Cloud vs:")
         -  Line 4 starts a more complex Count Loop. First off, we used
            the abbreviation for "count", which is just ``c``. We left
            ``numAttacks`` as is, but added a second *argument* - in
            this case, a different "separator." All loops in MapTool
            macros have a default separator, which is the comma.
            However, you don't always want to separate your results with
            a comma, right? In this situation, we want to separate them
            with a line break, so each result is on its own line in
            chat. So, we put the new separator in - an HTML line break
            character, or <br>.
         -  Line 4 also uses the CODE roll option, which is discussed in
            `Introduction to Macro
            Branching <Introduction_to_Macro_Branching>`__,
            and lets us do multiple operations as a single group.
         -  Line 6 sets the variable ``attack`` to the sum of
            ``attackBonus`` and 1d20.
         -  Line 7 sets the variable ``damage`` to the sum of ``1d6+2``.
         -  Line 8 is a combination of text and variables, which are
            output to chat. Note that the variable ``roll.count`` is in
            there, which will be replaced with whatever iteration the
            loop happens to be on.
         -  Line 9 closes the CODE block, and the whole command.

         The output from this would look something like:

            | Toxic Cloud vs:
            | Target 1: Attack 17; 6 damage.
            | Target 2: Attack 12; 5 damage.
            | Target 3: Attack 19; 7 damage.
            | Target 4: Attack 10; 3 damage.

         .. rubric:: WHILE: Keep On Keepin' On
            :name: while-keep-on-keepin-on

         Let's move on to a new looping structure:
         `[while():] <while_(roll_option)>`__. This
         structure is the first one we'll discuss that uses a
         *condition* to determine how many times to loop (previously,
         count used a value - but not a comparison of any kind). The
         general format of a
         `[while():] <while_(roll_option)>`__ loop is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [while(condition): command]

         You're probably getting used to reading these by now.

         -  `[while():] <while_(roll_option)>`__: of
            course, we need to add the roll option itself
         -  **condition**: this is the comparison that we make, to see
            if the loop needs to stop - it can be any of the logical
            comparisons we've discussed already (such as, ``loops < 10``
            or ``numDice > 5`` or anything you can think of).
         -  **command**: the macro command (or commands, if you use the
            CODE option) to run each time the loop goes 'round.

         So, if you read this, the while loop really just says, "while
         some condition is true, keep doing this." Let's look at some
         examples.

         .. rubric:: Example 1: Basic Countdown
            :name: example-1-basic-countdown

         This is a very basic example, just to illustrate the basic
         parts of the `[while():] <while_(roll_option)>`__
         loop. Suppose you wanted to count down from 10 to 1. There are
         many ways to do this, of course, but we'll do it with a
         `[while():] <while_(roll_option)>`__ loop. The
         macro would look like this:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:num = 10]

                  #. .. code-block:: none

                        [while(num > 0): num = num - 1]

         The above macro simply says that "while the variable ``num`` is
         greater than 0, subtract 1 from ``num``, and repeat." Each time
         through the loop, the value of ``num`` will be checked by
         MapTool. If it is greater than 0, it will let the command
         ``num = num-1`` happen, and display the result in chat; if
         ``num`` is *not* greater than 0, then the loop will be halted.
         The output of this macro looks like:

            9,8,7,6,5,4,3,2,1

         You'll note that "10" was never shown. That's because while the
         loop may have started with ``num`` having the value of 10, the
         first time we *see* any output is when the operation ``num -1``
         takes place - so the first thing we see is ``num - 1``, which
         is 9.

         .. rubric:: Example 2: The Machine-Gun
            :name: example-2-the-machine-gun

         Let's look at a more complicated (and perhaps more interesting)
         example. In this example, we won't be using the `Sample
         Ruleset <Sample_Ruleset>`__, mostly because I
         couldn't think of a useful example from that game. So, let's
         assume we have the following game situation:

         -  A character has a machine gun with 30 rounds of ammunition
         -  They may fire one to six rounds for every action
         -  If their attack roll of 1d20 is greater than 15, they may
            make another attack; otherwise, they must end their turn.
            They always get at least 1 attack, though.

         So what we need to do is repeat the operation until *either*
         the weapon runs out of ammo, or they roll less than a 15 on
         their attack. Here's how that macro would look:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:ammo = 30]

                  #. .. code-block:: none

                        [h:hit = 1]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [while(ammo > 0 && hit == 1, "<br>"),CODE:

                  #. .. code:: de2

                        {

                  #. .. code-block:: none

                          [h:attackRoll = 1d20]

                  #. .. code-block:: none

                          [h:ammoSpent = 1d6]

                  #. .. code-block:: none

                          [h,if(attackRoll > 15): hit = 1; hit = 0]

                  #. .. code-block:: none

                          [h:ammo = ammo - ammoSpent]

                  #. .. code:: de2

                          Your first attack expends [r:ammoSpent] rounds, and [if(hit==1, "hits.", "misses.")] You have [r:ammo] rounds remaining.

                  #. .. code-block:: none

                        }]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [if(hit==0): "Your turn ends because you missed a target."]

                  #. .. code-block:: none

                        [if(ammo==0): "Your turn ends because you are out of ammo."]

         Here's the breakdown of this macro:

         -  Line 1 and 2 set two important variables: ``ammo`` and
            ``hit``. We set ``ammo`` to 30, per the assumptions above,
            and we set ``hit`` to 1, so that the character always gets
            at least *one* attack roll (if we didn't set ``hit`` to 1,
            the loop might stop before it started!).
         -  Line 4 is the start of the While Loop: we establish the
            loop, and give it a combined condition. We say that *while*
            ``ammo`` has a value greater than 30, *and* (remember, two
            ampersands is the logical operator "and") ``hit`` *is equal
            to* 1, the loop should go 'round. If *either or both* of
            those is *not* true, then the loop should stop. Also, we set
            the separator to <br>, so that a new line will be printed
            each time the loop runs.
         -  Lines 5 - 9 handle the actual loop processing. Note that in
            that loop, we make sure to set a new value for ``hit`` and
            ``ammo`` - this is **critical**. If you never change the
            variables that your conditions are based on, then your loop
            will **never stop**.

         It's worth repeating: in a while loop, you **must change the
         variable that your condition is checking, or you can end up
         with a loop that never stops**.

         So, the output of this macro will look something like:

            | Your attack expends 6 rounds, and hits. You have 24 rounds
              remaining.
            | Your attack expends 2 rounds, and hits. You have 22 rounds
              remaining.
            | Your attack expends 3 rounds, and misses. You have 19
              rounds remaining. Your turn ends because you missed a
              target.

         .. rubric:: FOR: I Couldn't Think of Anything Catchy
            :name: for-i-couldnt-think-of-anything-catchy

         The next loop structure to address is the
         `[for():] <for_(roll_option)>`__ roll option.
         This option is somewhat similar to
         `[while():] <while_(roll_option)>`__, because it
         repeats a sequence of code a number of times based on a
         particular condition; it is also like
         `[count():] <count_(roll_option)>`__ because that
         particular condition is "has our counter reached a particular
         number yet?"

         The general format for a
         `[for():] <for_(roll_option)>`__ loop is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [for(counter, start, end, stepsize, separator): command]

         Here's how that breaks down:

         -  `[for():] <for_(roll_option)>`__: as always,
            we need to actually put the roll option in there
         -  **counter**: this is the variable that will be used to count
            the iterations through the loop; typically people us a
            simple 1-letter variable in here, like ``x`` or ``i``. For
            examples below, we'll use ``i``.
         -  **start**: this is what the ``counter`` variable starts at
            (it can be zero, another variable, or any other numeric
            value)
         -  **end**: this is the value that *ends* the loop

            -  In a loop where the ``counter`` variable is *increasing*
               - in other words, a loop with a positive ``stepsize`` -
               the loop runs as long as ``counter`` is *less than*
               ``end``
            -  In a loop where the ``counter`` variable is *decreasing*-
               in other words, a loop with a negative ``stepsize`` - the
               loop runs as long as ``counter`` is *greater than*
               ``end``

         -  **stepsize**: this is how big the increment is for each
            iteration of the loop (for example, if you set ``stepsize``
            to 2, then ``counter`` will increase by 2 ever iteration).
            The default stepsize is +1 (that is, by default, the
            ``counter`` variable increments by 1 each time the loop is
            processed).
         -  **separator**: like with
            `[count():] <count_(roll_option)>`__ and
            `[while():] <while_(roll_option)>`__, this is
            an optional separator to show between each output line from
            the loop; the default is a comma.

         .. rubric:: Example 1: Basic Countdown
            :name: example-1-basic-countdown-1

         This example illustrates how the
         `[for():] <for_(roll_option)>`__ option's various
         components work. As with the previous looping structure, this
         is a basic countdown:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [FOR(i,10,0,-2): "i is now " + i]

         In this example, we have specified all components of the loop:

         -  The counter variable is ``i``.
         -  The start value is ``10``
         -  The end value is ``0``
         -  The stepsize is ``-2`` (the counter *decrements* by 2 every
            time the loop processes)

         The output of this will look like:

            i is now 10, i is now 8, i is now 6, i is now 4, i is now 2

         You will note that there is no *i is now 0* step - this is
         because when the counter counts down to 0, ``i`` is no longer
         greater than 0.

         .. rubric:: Example 2: Creating a Table With Multiple Rows
            :name: example-2-creating-a-table-with-multiple-rows

         This example illustrates a practical use of the
         `[for():] <for_(roll_option)>`__ option to create
         a table that will be sent to chat, with a number of rows based
         on how many properties are in a String List.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:theList = "Strength, Endurance, Dexterity, Intelligence"]
                      
                     [h:numberOfRows = listCount(theList)]
                      
                     <table border="1">
                     [for(i, 0, numberOfRows, 1, ""):  "<tr><td>"+listGet(theList, i)+"</td></tr>"]
                     </table>

         The example above uses a few cool commands to generate the
         output.

         -  ``theList`` is simply a string list variable containing four
            elements
         -  `listCount() <listCount>`__ is a function
            that, when you put the name of a string list variable in it,
            will return the number of elements in the string list
         -  We create the beginning of an HTML table by using the
            <table> tag
         -  The `[for():] <for_(roll_option)>`__ loop here
            uses the counter variable ``i``, which starts at 0, and
            counts up until it reaches ``numberOfRows``. It increases by
            1 each loop, and the default separator has been changed to
            ``""`` so that no extraneous commas are printed to chat.
         -  Inside the loop, we
            `concatenate <Introduction_to_Macro_Writing#String_Concatenation>`__
            the HTML tags for table rows and table cells around the
            function `listGet() <listGet>`__. This
            function will retrieve, from a string list variable, the
            value of the element that is at the position specified in
            the second argument. In this case, we say, "get from the
            variable ``theList`` the value of the element that's in the
            same position as ``i``" - so that it starts with element 0
            (all lists start at item 0 in MapTool) and each time we loop
            through, it gets the next element.
         -  At the end, we close the table with the appropriate HTML
            tag.

         The output looks like this. If you add in several more elements
         to the variable ``theList``, the table will grow in size to
         accommodate the new elements.

            ============
            Strength
            Endurance
            Dexterity
            Intelligence
            ============

         .. rubric:: FOREACH: A Very Special FOR
            :name: foreach-a-very-special-for

         The `[for():] <for_(roll_option)>`__ loop
         structure lets you repeat a set of commands a specified number
         of times, with flexible beginning, ending, and steps. That
         looping method is applicable to many things, and can be looked
         at as a very "general" way to loop - it gives you lots of
         flexibility with where you start and end, and can be used for
         many operations.

         However, frequently loops are used to go through a list of
         items that is already established, and it is kind of a pain to
         have to make sure to count each list, then assign the variables
         in a `[for():] <for_(roll_option)>`__ loop, and
         make sure you can figure out how the ``counter`` variable
         corresponds to the position of an item in a list. So, a
         different kind of for loop - one that handles most of that
         without bothering *you* about it - also exists. This one is
         called `[foreach():] <foreach_(roll_option)>`__.

         In a `[foreach():] <foreach_(roll_option)>`__
         loop, the looping structure is given two arguments: the name of
         a string list, and a variable. The variable takes on the value
         of each element in the list, in turn, as the looping structure
         iterates. That's a bit confusing, so first, let's look at the
         general structure of a
         `[foreach():] <foreach_(roll_option)>`__ loop:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [foreach(item, list): command]

         -  `[foreach():] <foreach_(roll_option)>`__: once
            again, the roll option itself.
         -  **item**: this is the variable that takes on the value of
            each successive element in the list or property
         -  **list**: this is the string list you want the ``foreach()``
            to work on
         -  **command**: the operation you want performed on each
            successive ``item`` in ``list``

         To explain that in plain English: assume for a moment that
         there you have the names of several targets (NPC tokens) that
         your character wants to attack at the same time. You need to
         make an attack roll against each target, which is equal to 1d20
         + 7, but you have to roll separately for *each* target.

         You could write out the attacks each time like this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  I attack target 1: [1d20+7]<br>
                  I attack target 2: [1d20+7]<br>
                  I attack target 3: [1d20+7]<br>
                  I attack target 4: [1d20+7]<br>

         And so forth and so on. Not so bad if you have 3 targets. But
         what if you have 6? Or 12?

         So instead, what if you created a single variable that was a
         list of the names of each target? Then, you can use the
         `[foreach():] <foreach_(roll_option)>`__ loop to
         go through the list one by one and let you make the roll with a
         very efficient little bit of code.
         `[foreach():] <foreach_(roll_option)>`__ may be a
         little hard to explain, but once you understand what it can do,
         you will see how useful it can be!

         Now, let's jump to some examples.

         .. rubric:: Example 1: Listing the Contents of a String List
            :name: example-1-listing-the-contents-of-a-string-list

         This simple example will go through a string list, and list the
         value of each element in the list, from beginning to end.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:theList = "18, Bob, 29, Foo, 1009, Snorkel"]
                      
                     [foreach(item, theList, "<br>"): item]

         In the above macro, we've created a
         `[foreach():] <foreach_(roll_option)>`__ loop
         that takes the list variable ``theList``, and goes to each
         element in that list, and assigns the value of that element to
         the variable ``item``. We've set the separator to the HTML code
         for a line break, and then -- after the colon -- instructed the
         macro to print the value of the variable ``item`` to the chat
         window.

         The output of that macro looks like:

            | 18
            | Bob
            | 29
            | Foo
            | 1009
            | Snorkel

         Do you see what happened there? The foreach() option went to
         each element in ``theList``, said, "the variable ``item`` is
         now equal to the element," and then printed the value of
         ``item`` to chat.

         .. rubric:: Example 2: Attacking a Bunch of Bad Guys
            :name: example-2-attacking-a-bunch-of-bad-guys

         Now, let's look at the example described in the beginning.
         Remember how we had those target names to attack? Here's how
         we'd do that:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:targetList = "Orc 1, Goblin 2, Orc 4, Zombie 17, Big Boss"]
                      
                     [foreach(target, targetList, "<br>"),CODE:
                     {
                        [h:attackRoll = 1d20+7]
                        I attack [r:target] with an attack roll of [r:attackRoll]
                     }]

         -  The first line simply sets up the variable ``targetList``,
            as discussed.
         -  The foreach loop goes through each element in
            ``targetList``, assigning its value to the variable
            ``target``. So, the first time through, ``target`` has the
            value of the first item in ``targetList`` - in other words,
            ``target`` is equal to ``Orc 1``. The second time through,
            ``target`` equals the *second* item in the list, and so on.
         -  The `[code():] <code_(roll_option)>`__ roll
            option is used so we can execute multiple commands (and
            because it sometimes makes formatting the output a little
            easier)
         -  Inside the CODE brackets, we calculate a variable called
            ``attackRoll``. This is recalculated on every loop, so it's
            different for each ``target``.
         -  Finally, we generate some chat output, inserting the
            variable ``target`` and the variable ``attackRoll`` in the
            appropriate places.

         The output of that macro, when sent to chat, looks like:

            | I attack Orc 1 with an attack roll of 12
            | I attack Goblin 2 with an attack roll of 11
            | I attack Orc 4 with an attack roll of 21
            | I attack Zombie 17 with an attack roll of 17
            | I attack Big Boss with an attack roll of 9

         .. rubric:: Conclusion
            :name: conclusion

         That about covers the looping basics for MapTool macros. The
         examples shown above are very simple, of course - just enough
         to show you how these work. But looping is *incredibly* useful
         for many applications in a MapTool macro, from generating
         multiple die rolls to building tables to editing token
         properties, so make sure to experiment with it.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Macro_Loops&oldid=5699"

