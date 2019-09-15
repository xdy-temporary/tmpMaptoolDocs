=================================
switch (roll option) - MapToolDoc
=================================

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

   .. rubric:: switch (roll option)
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

            -  `1 [switch():] Roll
               Option <#.5Bswitch.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: [switch():] Roll Option
            :name: switch-roll-option

         .. container::

            \* **Introduced in version 1.3b46**

         Chooses among several options and executes code based on the
         expression.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [switch(expression):

               #. .. code-block:: none

                        case case1: body1;

               #. .. code-block:: none

                        case case2: body2;

               #. .. code-block:: none

                        default: defaultBody

               #. .. code:: de2

                     ]

         **Parameters**

         -  ``expression`` - The *regular expression* that determines
            which case is executed. Since this is a *regular
            expression*, metacharacters such as ``*`` and ``()`` will
            need to have backslashes in front of them if you want to
            match them literally.
         -  ``case`` - A potential match for the ``expression``,
            possesses a corresponding ``body`` that is executed if a
            match is made.
         -  ``default`` - If the ``expression`` finds no matches within
            the ``case``\ s, then the ``defaultBody`` is executed.

         **Notes**

         -  the ``case`` and ``default`` statements are the only
            case-sensitive statements in MapTool, thus ``CASE`` or
            ``Default`` will NOT work!
         -  strings in the ``case`` MUST be surrounded by "double
            quotes" as 'single quotes' will generate an error.

         .. rubric:: Examples
            :name: examples

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

                     case "daily": "You may only use this power once per day"]

         Outputs:

         ::

            You may use this power as much as you like

         | 

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

                     case "longsword": "a slashing weapon"]

         Outputs:

         ::

            used for jabs, so is a puncturing weapon

         Notice that the first matching clause was the one that the
         **[switch():]** option found.

         another example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [abort(input("number|0|enter a number"))]

               #. .. code-block:: none

                     [switch(number):

               #. .. code-block:: none

                        case 0: "you did not enter a number";

               #. .. code-block:: none

                       case 1: "you entered 1 as a number";

               #. .. code:: de2

                        case 2: "you entered 2 as a number";

               #. .. code-block:: none

                        default: "you entered a number not equal to 1 or 2"

               #. .. code-block:: none

                     ]

         When using the `[code():] <code_(roll_option)>`__
         option with a ``switch`` option, each ``case`` body has its own
         set of braces, like so:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,switch(class),code:

               #. .. code-block:: none

                     case "Warrior": {

               #. .. code-block:: none

                       [Armor = 6]

               #. .. code-block:: none

                       [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]

               #. .. code:: de2

                     };

               #. .. code-block:: none

                     case "Rogue": {

               #. .. code-block:: none

                       [Armor = 2]

               #. .. code-block:: none

                       [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]

               #. .. code-block:: none

                     };

               #. .. code:: de2

                     case "Wizard": {

               #. .. code-block:: none

                       [Armor = 1]

               #. .. code-block:: none

                       [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]

               #. .. code-block:: none

                     };

               #. .. code-block:: none

                     case "Priest": {

               #. .. code:: de2

                       [Armor = 4]

               #. .. code-block:: none

                       [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]

               #. .. code-block:: none

                     };

               #. .. code-block:: none

                     default: {

               #. .. code-block:: none

                       [Armor = 0]

               #. .. code:: de2

                       [beginningPowers = "Fists, Feet"]

               #. .. code-block:: none

                     }]

         .. rubric:: See Also
            :name: see-also

         `if() <if>`__,
         `[if():] <if_(roll_option)>`__, `Introduction to
         Macro
         Branching <Introduction_to_Macro_Branching>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=switch_(roll_option)&oldid=6200"

