=============================
explodingSuccess - MapToolDoc
=============================

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

   .. rubric:: explodingSuccess
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

            -  `1 explodingSuccess()
               Function <#explodingSuccess.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: explodingSuccess() Function
            :name: explodingsuccess-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; returns the
            count of dice rolls that are above a certain number, while
            each individual dice rolled at maximum value will be
            rerolled with the new roll added to the old. There is no
            limit to the number of time that that an individual dice
            rolled can be rerolled by this function, but the odds of
            each individual number decreases as the total increases past
            the number of sides.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     explodingSuccess(times, sides, target)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.
         -  ``target`` - The number that a dice needs to be equal to or
            higher to be considered a success(added to the count
            returned).

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll a twenty-sided dice, and returns ``1`` if rolled higher
            than ``30``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: explodingSuccess(1, 20, 30)]

            Returns ``0`` or ``1``; ``1`` is only returned if the
            twenty-sided dice rolls ``20`` and then is
            rerolled(exploded) with a result equal to or higher than
            ``10``.

            Roll five ten-sided dice, and returns the number of dice
            that rolled higher than twenty, using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 5]

                  #. .. code-block:: none

                        [h: DiceSides = 10]

                  #. .. code-block:: none

                        [h: DiceTarget = 20]

                  #. .. code-block:: none

                        [t: explodingSuccess(DiceTimes, DiceSides, DiceTarget)]

            Returns a number than is between ``0`` and ``5``.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            For another method of rolling dice, see `Dice
            Expressions </rptools/wiki/Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=explodingSuccess&oldid=3071"

