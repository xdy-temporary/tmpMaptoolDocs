=====================
herostun - MapToolDoc
=====================

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

   .. rubric:: herostun
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
         from\ `hero </maptool/index.php?title=hero&redirect=no>`__\ )

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

            -  `1 herostun() Function <#herostun.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: herostun() Function
            :name: herostun-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; acts like a
            standard `roll() <roll>`__ with the difference
            being that a hidden variable is tracked, which can then be
            returned using `herobody() <herobody>`__. This
            hidden variable is calculated by adding ``2`` for each dice
            that is rolled at maximum value, ``0`` for each dice that is
            rolled at minimum value, and ``1`` for each dice that is
            rolled at neither minimum, nor maximum value.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herostun(times, sides)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hero(times, sides)

         **Parameters**

         -  ``times`` - The number of times to roll the dice.
         -  ``sides`` - The number of sides the dice possess.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll a twenty-sided dice, and return the
            `herobody() <herobody>`__ result as well.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: herostun(1, 20)] - [t: herobody(1, 20)

            Returns a number that is between ``1`` and ``20`` for the
            herostun roll, and a number between ``0`` and ``2`` for the
            herobody roll.

            Roll five ten-sided dice, and return the
            `herobody() <herobody>`__ result as well,
            using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: DiceTimes = 5]

                  #. .. code-block:: none

                        [h: DiceSides = 10]

                  #. .. code-block:: none

                        [t: herostun(DiceTimes, DiceSides)] - [t: herobody(DiceTimes, DiceSides)]

            Returns a number than is between ``5`` and ``50`` for the
            herostun roll, and a number between ``0`` and ``10`` for the
            herobody roll.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            Used in conjunction with
            `herobody() <herobody>`__
            For another method of rolling dice, see `Dice
            Expressions <Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=herostun&oldid=3076"

