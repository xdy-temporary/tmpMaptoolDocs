=================
roll - MapToolDoc
=================

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

   .. rubric:: roll
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `dice </maptool/index.php?title=dice&redirect=no>`__\ )

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

            -  `1 roll() Function <#roll.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: roll() Function
            :name: roll-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls. You may also
            think of this function as a method of generating a random
            number between ``times`` and ``times*sides``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     roll(times, sides)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     dice(times, sides)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     d(times, sides)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.

         **Note:**

         The roll function does not keep track of the individual dice
         rolled. In other words their results are lost, just the total
         is kept. How to roll dice when individual dice matter is shown
         in the examples.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Roll a twenty-sided dice**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: roll(1, 20)]

            Returns a number that is between ``1`` and ``20``.

            | 
            | **Roll five ten-sided dice, using variables**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 5]

                  #. .. code-block:: none

                        [h: DiceSides = 10]

                  #. .. code-block:: none

                        [t: roll(DiceTimes, DiceSides)]

            Returns a number than is between ``5`` and ``50``.

            | 
            | **Throw multiple dice**

            ...and sort and sum the result. Note that roll() doesnt help
            with this. You have to roll individual dice and keep track
            yourself. Gladly MapTool does help with loops and
            listkeeping functions.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h: diceTimes = 5]
                     [h: diceSides = 6]
                     [h: listOfRolls = ""]
                     [h: sum = 0]
                     [h, count(diceTimes), code: {
                         [h: r = roll(1, diceSides)]
                         [h: sum = sum+r]
                         [h: listOfRolls = listAppend(listOfRolls, r)]
                     }]
                     You rolled [r: listSort(listOfRolls, "N-")] = [r: sum].

            Rolls 5 times a d6 and returns these as sorted list as well
            as the total.

            **See also**
            `[count():] <count_(roll_option)>`__,
            `listAppend() <listAppend>`__ and
            `listSort() <listSort>`__.
             

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            For another method of rolling dice, see `Dice
            Expressions <Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=roll&oldid=5877"

