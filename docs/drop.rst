=================
drop - MapToolDoc
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

   .. rubric:: drop
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

            -  `1 drop() Function <#drop.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: drop() Function
            :name: drop-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; returns the
            total of a dice roll that ignores a certain number of the
            lowest dice rolled.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     drop(times, sides, ignore)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.
         -  ``ignore`` - The number of lowest rolls that are ignored
            when totaling the roll.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll ten twenty-sided dice, ignoring the lowest five rolls.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: drop(10, 20, 5)]

            Returns a number that is between ``5`` and ``100``, with a
            high average.

            Roll five ten-sided dice ignoring the lowest two rolls,
            using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 5]

                  #. .. code-block:: none

                        [h: DiceSides = 10]

                  #. .. code-block:: none

                        [h: DiceIgnore = 2]

                  #. .. code-block:: none

                        [t: drop(DiceTimes, DiceSides, DiceIgnore)]

            Returns a number than is between ``3`` and ``30``, with a
            high average.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            For another method of rolling dice, see `Dice
            Expressions <Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=drop&oldid=3067"

