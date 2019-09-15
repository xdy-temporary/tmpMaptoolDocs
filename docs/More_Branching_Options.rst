===================================
More Branching Options - MapToolDoc
===================================

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

   .. rubric:: More Branching Options
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

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/More_Branching_Options/ja>`__\ 

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
            -  `3 MACRO: Running Other
               Macros <#MACRO:_Running_Other_Macros>`__

               -  `3.1 What's It Do? <#What.27s_It_Do.3F>`__
               -  `3.2 Why would I Use It? <#Why_would_I_Use_It.3F>`__
               -  `3.3 Common Tasks from Multiple
                  Pathways <#Common_Tasks_from_Multiple_Pathways>`__
               -  `3.4 Tasks Everyone Does <#Tasks_Everyone_Does>`__
               -  `3.5 Manipulating Other Tokens and Trusted
                  Macros <#Manipulating_Other_Tokens_and_Trusted_Macros>`__
               -  `3.6 How Do I Use It? <#How_Do_I_Use_It.3F>`__
               -  `3.7 Working with Arguments and
                  Returns <#Working_with_Arguments_and_Returns>`__

                  -  `3.7.1 The Special Variable
                     macro.args <#The_Special_Variable_macro.args>`__
                  -  `3.7.2 The Special Variable
                     macro.return <#The_Special_Variable_macro.return>`__

               -  `3.8 Side by Side Examples <#Side_by_Side_Examples>`__

         .. rubric:: Introduction
            :name: introduction

         This is a guide to the "advanced" macro branching option,
         `[macro():] </rptools/wiki/macro_(roll_option)>`__.

         .. rubric:: Assumptions
            :name: assumptions

         This assumes you have an understanding of what a roll option
         is, and that you've read the preceding tutorials.

         Also, don't forget to enable the *Use ToolTips for Inline
         Rolls* option in MapTool Preferences.

         .. rubric:: MACRO: Running Other Macros
            :name: macro-running-other-macros

         One of the best practices when you write macros - especially
         when they become complex - is to keep them streamlined and
         lean, and only have them do what they need to do - for
         instance, if you have a macro that adds a skill to a token, it
         doesn't need to be the same macro that checks to see if an
         attack hits, or records damage taken. It just adds skills.

         Writing macros this way - each macro doing something relatively
         small - is a good way to keep yourself organized and keep your
         macros clear (it also makes them easier to fix if something
         goes wrong!). What's more, it helps keep your memory use lower,
         so you don't get run into `stack overflow
         errors </rptools/wiki/Stack_Size>`__ or, more commonly, slow
         macros.

         But if you do this, how can you make one macro run based on
         another one - surely, you don't want to have to hit each button
         every time something happens, right? Enter the
         `[macro():] </rptools/wiki/macro_(roll_option)>`__ roll option.

         .. rubric:: What's It Do?
            :name: whats-it-do

         The `[macro():] </rptools/wiki/macro_(roll_option)>`__ roll
         option is they way you can have one macro - the *calling* macro
         - trigger another macro, which we call the *called* macro. The
         *calling* macro can send some information to the *called*
         macro, where that information will be handled and processed and
         probably changed, and then, if you like, the *called* macro can
         send some information back to the caller.

         .. rubric:: Why would I Use It?
            :name: why-would-i-use-it

         Where this comes in handy is in three circumstances: first,
         when you have some operation that you're always doing, but you
         have several different ways that it might come up. Second, if
         you have a macro that *everyone* uses. The third, and more
         powerful use, is when you want to manipulate another token
         besides your own - then you frequently need to use *called*
         macros, because there are some things only a *called* macro can
         do!

         .. rubric:: Common Tasks from Multiple Pathways
            :name: common-tasks-from-multiple-pathways

         Let's look at the first benefit: take, for example, a macro
         that applies damage to a token in accordance with the `Sample
         Ruleset </rptools/wiki/Sample_Ruleset>`__ (in other words, it
         looks at a token's properties, and then deducts damage from the
         token's ``HitPoints`` property). How many ways can you think a
         token might get damaged?

         #. It could get damaged by an attack from an enemy
         #. It could get damaged by an attack from a friend (accidental
            or otherwise)
         #. It could get damaged by falling
         #. It could be damaged by a trap

         All kinds of ways. Now, suppose you have three macro to handle
         damage. These macros are called **Enemy Attack**, **Friendly
         Fire**, and **Environmental Damage**. Each of these causes a
         token's ``HitPoints`` to be reduced, but each also has some
         special processing to determine *just how much* HP reduction
         takes place (it's not important what the special processing is
         at the moment).

         So you have three macros, but each has a common element: they
         all in the end reduce the token's ``HitPoints``. Consider a
         couple alternatives - you can:

         #. Write each macro separately, including the calculations to
            reduce ``HitPoints``; or
         #. Write a fourth macro, containing just the calculations to
            reduce ``HitPoints``, and have the three damage handler
            macros *call* that fourth to handle the final calculations.

         The advantages of the first option are that you only need to
         write three macros, and you're done. On the other hand, what if
         you realize you made a mistake in your damage macro? You then
         have to edit it in three places. In the second option, you only
         edit one copy of the damage macro.

         .. rubric:: Tasks Everyone Does
            :name: tasks-everyone-does

         Building on the example above, if you have a whole bunch of
         macros that everyone uses (perhaps everyone needs to have a way
         to attack, to defend, and to take and heal damage), you can
         create a single set of macros that everyone simply *calls*,
         rather than duplicating every macro on every token, every time
         you need a new token on the map.

         So, for example, you may want to build a "library" of macros to
         handle your game (whatever game it happens to be), and then
         create a single set of macros on your tokens that do nothing
         but *call* macros in the library.

         You'll note that it doesn't mean you have fewer macros overall
         - every token still needs a set of macros to call on the
         library; however, it *does* mean that your actual complex
         macros (the ones that took you a long time to write) are all in
         one place, and you only need to alter **one** copy in order to
         fix an error. If you'd copied the entire macro set to every
         token, you'd have to fix *every single token* one at a time to
         fix any mistakes you made.

         .. rubric:: Manipulating Other Tokens and Trusted Macros
            :name: manipulating-other-tokens-and-trusted-macros

         Generally, when a token runs a macro, or calls a macro, the
         macro assumes that all properties and variables it needs to use
         apply to the token *running* the macro. So if Bork the Brave
         calls a macro in a macro library, that library macro is going
         to assume that it needs to do its thing on Bork the Brave.

         However, sometimes Bork the Brave does *not* want this - maybe
         Bork the Brave just whacked a troll with his sword, and wants
         the damage to be applied to the troll (and, by extension, most
         definitely does *not* want the damage applied to himself!).
         He's going to want a macro that will affect the *troll's*
         token, not his own.

         As it turns out, however, there are some things, as mentioned,
         that a regular old macro on a player token simply can't do. For
         instance, a macro on a player token can't go and determine what
         an NPC token's properties are. It's simply not permitted to
         access another token. I think you'll agree this is a good way
         to go - you may not want players being able to see property
         values on an NPC. Furthermore, a player token macro can't
         *change* values on another token. Nobody wants the players to
         be able to, for instance, reduce an enemy's armor value to zero
         just before making an attack.

         But still, we want to be able to do *some* things to other
         tokens, right? In response to that, the concept of **trusted
         macros** was developed. Trusted macros are simply macros that
         can perform certain functions unavailable to other macros, such
         as the functions that manipulate token properties *other than*
         the ones on the token who called the macro.

         .. rubric:: How Do I Use It?
            :name: how-do-i-use-it

         `[macro():] </rptools/wiki/macro_(roll_option)>`__ is a roll
         option, so, like other roll options you've seen, it is put at
         the beginning of a line and ends with a colon. The essential
         format of the
         `[macro():] </rptools/wiki/macro_(roll_option)>`__ roll option
         is:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [MACRO("macroName@Lib:token"): macro_arguments]

         In the above example, there are several parts:

         -  The opening and closing square brackets (**[ ]**), which
            surround *all* macro commands in MapTool
         -  The word "MACRO" (it does not have to be capitalized; that's
            done to keep it noticeable!), which is just the name of this
            particular roll option
         -  *macroName*: this is the name of the macro you wish to call
         -  @: this is used in the same sense as in an email address -
            it means "at"
         -  **Lib:token**: this is the `Library
            Token </rptools/wiki/Library_Token>`__ that contains the
            macro you wish to call. Library tokens are a complex
            subject, but you can think of them as a single token that
            holds a "library" of macros, that can be called by other
            tokens or call each other.
         -  **macro_arguments**: an *argument* is a programming term for
            information that you send to a function (or in this case, a
            macro) that you want the function to *do* something to. If
            you had a function that added two numbers together, the
            numbers you send to it would be the "arguments" to that
            function.

         So in the command above, you've said "run the macro called
         *macroName* at the library token *Lib:token*, and send it
         *macro_arguments* to work on." The programming jargon for what
         you've just done is "calling a macro," or "creating a macro
         call."

         The next section will have some actual examples to help you get
         a grasp of using ``[MACRO():]``.

         .. rubric:: Working with Arguments and Returns
            :name: working-with-arguments-and-returns

         In programming terms, a function is a set of commands that
         *receives* arguments (described briefly above), does some
         processing on those arguments, and then *returns* a value to
         the place from where it was called. The macro roll option is
         not technically a function, but when it is used, the process is
         mostly similar: it calls on another macro, sends it arguments,
         and that other macro *may* - if you write the macro so that it
         does - return a value to the calling macro.

         When you call a macro, you can send it any variable, string, or
         number as an argument (in other words, you can replace
         *macro_arguments* with a variable, a string, or a number, which
         is sent to the called macro). For example, let us assume the
         following:

         -  There is a `Library Token </rptools/wiki/Library_Token>`__
            called "'Lib:MT **which has a macro called** Use
            Power\ **.**
         -  You have a token for Bork the Brave, which has a macro
            called **Shield Bash**. This is one of Bork's powers.
         -  You want to send the name of the power to **Use Power**,
            which will run the standard procedures to resolve the use of
            a power.

         To have Bork's macro trigger the **Use Power** macro on
         **Lib:MT**, you would create a macro called "Shield Bash",
         which contained the following command:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [macro("Use Power@Lib:MT"): "Shield Bash"]

         So, that's great. You've sent this information off to the macro
         **Use Power**. But...how does **Use Power** recognize what you
         sent it?

         .. rubric:: The Special Variable macro.args
            :name: the-special-variable-macro.args

         Whenever you create a macro call and execute it, a special
         variable called ``macro.args`` is created. This variable is
         visible (that is, can be accessed, changed, or read) only by
         the macro being called, and it contains whatever you
         substituted in for *macro_arguments*. So, in our example above,
         ``macro.args`` is equal to "Shield Bash". So, for example, in
         the macro **Use Power**, you might have a line that says:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [h:powerName = macro.args]

         What that line says is, "in this macro, take the value of
         ``macro.args``, and assign it to the variable ``powerName``."
         From then on out, the variable ``powerName`` will have the
         value "Shield Bash" (if we continue our example from above).
         Note that you don't *have* to do this - you can also just refer
         to ``macro.args`` wherever you need to.

         The macro being called can then use this special variable
         ``macro.args`` like any other variable - it can read it, it can
         change it, it can add it to something - anything you would do
         with a variable. You could even ignore it!

         Of course, if you've sent information in one direction - from
         the caller to the callee, so to speak - what if you need to
         send information the other way (in other words, *return* a
         value)?

         .. rubric:: The Special Variable macro.return
            :name: the-special-variable-macro.return

         In the macro that is being called, you can do a lot of
         processing on the variable ``macro.args``. You can output text
         to chat and update token properties, even. But you migh also
         want the results of all that processing to be sent *back* to
         the calling macro - maybe you use it to create *part of* a
         string, and you need to send that piece back to be assembled
         into the final output you want to send to chat.

         In that case, you can assign whatever value you want to send
         back to the variable ``macro.return``, which will be sent back
         to the calling macro. Assume, then, that the macro **Use
         Power** creates a variable called ``powerResultText`` that
         needs to be sent *back* to Bork's macro **Shield Bash** before
         it finishes. To do this, somewhere at the end of **Use Power**,
         you'd add this line:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code:: de1

                     [h:macro.return = powerResultText]

         You've said in that line that the special variable
         ``macro.return`` will be equal to whatever ``powerResultText``
         is set to, and **Shield Bash** can then use the variable
         ``macro.return`` for further processing.

         .. rubric:: Side by Side Examples
            :name: side-by-side-examples

         The examples below are the two macros discussed above, side by
         side, to illustrate the use of macro calls and the
         ``macro.args`` and ``macro.return`` variables. Make sure to
         check out the `Sample Ruleset </rptools/wiki/Sample_Ruleset>`__
         if you're not familiar with some of the various game terms.
         Also, note that these are not *complete* macros that include
         all of the possible classes and powers in the game, but a
         sampling to illustrate the use of ``[MACRO():]``.

         +-----------------------------------+-----------------------------------+
         | Shield Bash Macro                 | Use Power Macro                   |
         +===================================+===================================+
         | .. container::                    | .. container::                    |
         | mw-geshi mw-code mw-content-ltr   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |    .. container::                 |    .. container::                 |
         |    mtmacro source-mtmacro         |    mtmacro source-mtmacro         |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |             <!-- Call the Use Pow |             <!-- Receive macro ar |
         | er macro -->                      | guments -->                       |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             [h:powerName = macro. |
         |                                   | args]                             |
         |       #. .. code:: de1            |                                   |
         |                                   |       #. .. code:: de1            |
         |             [MACRO("Use Power@Lib |                                   |
         | :MT"): "Shield Bash"]             |                                   |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             <!-- Do a switch to f |
         |                                   | ind the power's Attack Bonus -->  |
         |       #. .. code:: de2            |                                   |
         |                                   |       #. .. code:: de2            |
         |             <!-- Receive the vari |                                   |
         | able macro.return after Use Power |             [h,switch(powerName): |
         |  has finished processing.-->      |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |             case "Sword": attackB |
         |                                   | onus = 2;                         |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |             [h:hitValue = macro.r |             case "Bow":  attackBo |
         | eturn]                            | nus = 0;                          |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             case "Shield Bash": a |
         |                                   | ttackBonus = -1;]                 |
         |       #. .. code:: de1            |                                   |
         |                                   |       #. .. code:: de1            |
         |             <!-- Use IF to check  |                                   |
         | the value of hitValue, and choose |                                   |
         |  an option -->                    |                                   |
         |                                   |       #. .. code:: de2            |
         |       #. .. code:: de2            |                                   |
         |                                   |             <!--Make the Attack R |
         |                                   | oll-->                            |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |             [h,if(hitValue == 1), |                                   |
         | CODE:                             |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |             [h:attackRoll = 1d20  |
         |             {                     | + Strength + attackBonus]         |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |               [damageRoll = floor |                                   |
         | ((1d6+Strength)/2)]               |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |             <!-- Check to see if  |
         |               [special = "Roll 1d | the attack succeeds (a roll of 15 |
         | 6. On a 4 or better, the foe is s |  or higher is a hit) -->          |
         | tunned for three rounds."]        |                                   |
         |                                   |       #. .. code:: de2            |
         |       #. .. code:: de2            |                                   |
         |                                   |                                   |
         |             };                    |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |             [h,if(attackRoll >= 1 |
         |             {                     | 5),CODE:                          |
         |                                   |                                   |
         |       #. .. code:: de1            |       #. .. code:: de1            |
         |                                   |                                   |
         |               [damageRoll = "None |             {                     |
         | "]                                |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |               [successText = "a s |
         |               [special = "No spec | uccess!"]                         |
         | ial effect."]                     |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |               [hit = 1]           |
         |             }]                    |                                   |
         |                                   |       #. .. code:: de2            |
         |       #. .. code:: de2            |                                   |
         |                                   |             };                    |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |             {                     |
         |             <!-- Display the Dama |                                   |
         | ge result and special effect -->  |       #. .. code:: de1            |
         |                                   |                                   |
         |       #. .. code:: de1            |               [successText = "a f |
         |                                   | ailure."]                         |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |       #. .. code:: de1            |                                   |
         |                                   |               [hit = 0]           |
         |             <b>Damage: </b> [r:da |                                   |
         | mageRoll]<br>                     |       #. .. code:: de1            |
         |                                   |                                   |
         |       #. .. code:: de1            |             }]                    |
         |                                   |                                   |
         |             <b>Special: </b> [r:s |       #. .. code:: de2            |
         | pecial]                           |                                   |
         |                                   |                                   |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             <!--Display the attac |
         |                                   | k result and the success, and the |
         |                                   | n send                            |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |              back the success inf |
         |                                   | o for final processing-->         |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                                   |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             The [r:powerName] att |
         |                                   | ack is [r:successText].<br>       |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |             [h:macro.return=hit]  |
         +-----------------------------------+-----------------------------------+

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/More_Branching_Options/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=More_Branching_Options&oldid=5698"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Intermediate </rptools/wiki/Category:Intermediate>`__
            -  `MapTool </rptools/wiki/Category:MapTool>`__
            -  `Tutorial </rptools/wiki/Category:Tutorial>`__

         --------------

         `Intermediate </rptools/wiki/Category:Intermediate>`__
         `MapTool </rptools/wiki/Category:MapTool>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Tutorial </rptools/wiki/Category:Tutorial>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=More+Branching+Options>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/More_Branching_Options>`__
            -  `Discussion </maptool/index.php?title=Talk:More_Branching_Options&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/More_Branching_Options>`__
            -  `View
               source </maptool/index.php?title=More_Branching_Options&action=edit>`__
            -  `View
               history </maptool/index.php?title=More_Branching_Options&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/More_Branching_Options>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/More_Branching_Options>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=More_Branching_Options&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=More_Branching_Options&oldid=5698>`__
            -  `Page
               information </maptool/index.php?title=More_Branching_Options&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `日本語 <http://lmwcs.com/rptools/wiki/More_Branching_Options/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 24 August 2011, at 06:17.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
