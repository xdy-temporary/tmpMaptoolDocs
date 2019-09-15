=========================
countsuccess - MapToolDoc
=========================

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

   .. rubric:: countsuccess
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
         from\ `success </maptool/index.php?title=success&redirect=no>`__\ )

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

            -  `1 countsuccess()
               Function <#countsuccess.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: countsuccess() Function
            :name: countsuccess-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; returns the
            count of dice rolls that are above a certain target number.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     countsuccess(times, sides, target)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     success(times, sides, target)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.
         -  ``target`` - The number that a dice needs to be equal to or
            higher to be considered a success.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll twenty ten-sided dice, and return the number that are
            above five.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: countsuccess(20, 10, 5)]

            Returns a number that is between ``0`` and ``20``, which is
            the number of dice that rolled higher than ``5``.

            Roll twelve six-sided dice, and return the number that are
            above three, using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 12]

                  #. .. code-block:: none

                        [h: DiceSides = 6]

                  #. .. code-block:: none

                        [h: DiceSuccess = 3]

                  #. .. code-block:: none

                        [t: countsuccess(DiceTimes, DiceSides, DiceSuccess)]

            Returns a number than is between ``0`` and ``12``, which is
            the number of dice that rolled higher than ``3``.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            For another method of rolling dice, see `Dice
            Expressions <Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=countsuccess&oldid=3070"

