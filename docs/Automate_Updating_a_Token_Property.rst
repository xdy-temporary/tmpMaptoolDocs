===============================================
Automate Updating a Token Property - MapToolDoc
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

   .. rubric:: Automate Updating a Token Property
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

         This section expects that you are already familiar with how to
         add `macro
         buttons <Introduction_to_Macro_Writing>`__ to the
         MapTool user interface.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Example: Updating Hit
               Points <#Example:_Updating_Hit_Points>`__
            -  `2 Example: Let's Rest for a
               Minute... <#Example:_Let.27s_Rest_for_a_Minute...>`__
            -  `3 Example: One Macro to Rule Them
               All <#Example:_One_Macro_to_Rule_Them_All>`__

         .. rubric:: Example: Updating Hit Points
            :name: example-updating-hit-points

         Let's say you have a property to represent hit points. We'll
         call our property ``HP``. Now we want some easy way to update
         ``HP``, so we're going to create a `macro
         button <Macro_Button>`__ that executes a
         `macro <Introduction_to_Macro_Writing>`__.

         First, consider how you want this to work. We want a window to
         popup on the screen and ask the user to enter a number. That
         number will be subtracted from ``HP``, so the user can use a
         positive number to represent damage and a negative number to
         represent healing. (We'll show another approach later.)

         The first step will be to prompt for the number. MapTool has
         this ability built-in. All we need to do is use a variable name
         that doesn't exist yet and MapTool will popup the prompt! The
         name of the variable is part of the prompt, so we'll use a
         descriptive name. How about ``AmountOfDamage``?

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ damage = AmountOfDamage ]

         Notice the extra variable name and the equals sign? That tells
         MapTool to calculate whatever is on the right of the equals
         sign and store the result into the variable on the left. In
         this case, there's no formula, so this becomes simply a copy --
         from the variable ``AmountOfDamage`` to ``damage``. But when
         MapTool tries to read the value of the variable and it doesn't
         exist, the popup will automatically appear! That's perfect for
         what we want!

         Now the next step is to subtract that from the ``HP`` property.
         Fortunately, what you learned in the last paragraph can be used
         again:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ damage = AmountOfDamage ]

               #. .. code-block:: none

                     [ HP = HP - damage ]

         This time the second line calculates the formula on the right
         (``HP - damage``) and stores the result into ... ``HP``? Isn't
         that going to screw up our ``HP`` value?

         No, it doesn't screw it up, but it does *replace* that value
         with the result. And because ``HP`` is a property, the result
         is stored back into the token's property. If you were to
         right-click on the token and save it to an external file, the
         new value of ``HP`` is stored with it. When the token is later
         reloaded, that value will come with it.

         If you want to add to the hit points instead, you have two
         choices: either the user can enter a negative number, or you
         can change the ``-`` to a ``+``. The first option is easy
         because it puts the burden on the user! The second option is
         really an option -- who wants to edit their macro every time
         they want to switch from damage to healing? Another choice not
         listed above would be to create a second macro. Then there
         could be one macro for adding damage and one for adding
         healing.

         There's a few things still needed here to make this a little
         prettier, but those are future steps. Go ahead and try this out
         right now on a token that you create in MapTool. (The default
         property type, *Basic*, includes a property named ``HP``.) And
         try adding the second macro as well, just for the practice.
         (Believe me, the more practice you get early in the process,
         the easier it will become later on.)

         .. rubric:: Example: Let's Rest for a Minute...
            :name: example-lets-rest-for-a-minute...

         So let's say that you now have a macro button that prompts you
         to change the token's hit points through damage or healing as
         described above. How do we reset their hit points to their
         maximum when they rest?

         We already know that we have a ``HP`` and ``HPmax`` properties,
         so when they are healed up we simply need to copy the value in
         ``HPmax`` into ``HP``. That should give you what you need to
         create a simple one-line macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ HP = HPmax ]

         Simple, right? But for the sake of argument, let's expand on
         this a bit. Instead of restoring all of the hit points to the
         creature, we will prompt the user for the number of hours that
         the creature will be resting. For my demonstration, I'm
         assuming that there's a property named ``Level``. If it rests
         for less than 24 hours, it gets back ``Level*2`` hit points. If
         it rests for 24 hours or more, it gets back ``Level*6``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ hours = NumberOfHours ]

               #. .. code-block:: none

                     [ healing = if(hours < 24, Level * 2, Level * 6) ]

               #. .. code-block:: none

                     [ HP = HP + healing ]

         You may notice the `if() <if>`__ function on the
         second line. One word of warning when using the
         `if() <if>`__ function: both the true and the
         false sections are executed! For that reason, you may want the
         `[if():] <if_(roll_option)>`__ roll option
         instead. Note that the syntax is slightly different between the
         two, so be careful about which one you choose.

         .. rubric:: Example: One Macro to Rule Them All
            :name: example-one-macro-to-rule-them-all

         Okay, so let's say you want to have one macro to handle all
         your healing needs. Using D&D 4th Edition, for example, you
         can:

         -  spend a Healing Surge and regain HP
         -  spend a Healing Surge without gaining HP
         -  gain HP as if you spent a Healing Surge
         -  gain a set number of HP (alone or in addition to a Healing
            Surge)
         -  gain Temporary HP (alone or in addition to a Healing Surge,
            and temporary HPs don't stack)

         Using the simple variable prompt explained above becomes
         clumsy, so let's use the `input() <input>`__
         function instead:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ cancel = input("SpendSurge | 1 | Spend Healing Surge? | CHECK",

               #. .. code-block:: none

                                      "GainSurge | 1 | Gain Surge HP? | CHECK",

               #. .. code-block:: none

                                      "ExtraHeal | 0 | Additional Healing",

               #. .. code-block:: none

                                      "GainTempHP | 0 | Temporary Hit Points") ]

               #. .. code:: de2

                     [ abort(cancel) ]

         This will prompt you for all possible variations detailed
         above, in a single input screen. ((image needed)) Then, you can
         use some `if() <if>`__ functions or
         `[if():] <if_(roll_option)>`__ roll options to
         update all the properties involved. This example assumes that
         you're using the token properties ``HP``, ``TempHP``,
         ``SurgeRemain`` and ``SurgeValue``:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ cancel = input("SpendSurge | 1 | Spend Healing Surge? | CHECK",

               #. .. code-block:: none

                                      "GainSurge | 1 | Gain Surge HP? | CHECK",

               #. .. code-block:: none

                                      "ExtraHeal | 0 | Additional Healing",

               #. .. code-block:: none

                                      "GainTempHP | 0 | Temporary Hit Points") ]

               #. .. code:: de2

                     [ abort(cancel) ]

               #. .. code-block:: none

                     [ if(SpendSurge): SurgeRemain = SurgeRemain - 1 ]

               #. .. code-block:: none

                     [ if(GainSurge): HP = HP + SurgeValue ]

               #. .. code-block:: none

                     [ HP = HP + ExtraHeal ]

               #. .. code-block:: none

                     [ TempHP = max(TempHP, GainTempHP) ]

         Notice that the `abort() <abort>`__ function was
         used after the `input() <input>`__ function to
         make sure that, in case the user clicked "Cancel" in the input
         window, the properties wouldn't be updated.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Automate_Updating_a_Token_Property&oldid=5606"

