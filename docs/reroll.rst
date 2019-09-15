===================
reroll - MapToolDoc
===================

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

   .. rubric:: reroll
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

            -  `1 reroll() Function <#reroll.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: reroll() Function
            :name: reroll-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; returns a
            dice roll similar to `roll() <roll>`__ with
            the difference being that each dice rolled that is lower
            than the ``minimum`` parameter is rerolled until it is at
            least the ``minimum``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     reroll(times, sides, minimum)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.
         -  ``minimum`` - The lowest number a dice rolled can return
            without being rerolled.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll five ten-sided dice, rerolling any dice rolled lower
            than five.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: reroll(5, 10, 5)]

            Returns a number that is between ``25`` and ``50``.

            Roll five ten-sided dice, rerolling any dice rolled lower
            than five, using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 5]

                  #. .. code-block:: none

                        [h: DiceSides = 10]

                  #. .. code-block:: none

                        [h: DiceMinimum = 5]

                  #. .. code-block:: none

                        [t: roll(DiceTimes, DiceSides, DiceMinimum)]

            Returns a number than is between ``25`` and ``50``.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            For another method of rolling dice, see `Dice
            Expressions <Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=reroll&oldid=3083"

