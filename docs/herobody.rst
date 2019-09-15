=====================
herobody - MapToolDoc
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

   .. rubric:: herobody
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

            -  `1 herobody() Function <#herobody.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: herobody() Function
            :name: herobody-function

         .. container:: template_description

            Generates random numbers to emulate dice rolls; this is the
            partner function to `herostun() </rptools/wiki/herostun>`__.
            The parameters used when calling this function must be
            exactly the same as the parameters used when calling
            `herostun() </rptools/wiki/herostun>`__, and it must be
            called during the same macro as
            `herostun() </rptools/wiki/herostun>`__ or an error will
            result. Refer to `herostun() </rptools/wiki/herostun>`__ for
            full usage details.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herobody(times, sides)

         **Parameters**

         -  ``times`` - The same ``times`` parameter that was used when
            calling `herostun() </rptools/wiki/herostun>`__.
         -  ``sides`` - The same ``sides`` parameter that was used when
            calling `herostun() </rptools/wiki/herostun>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Roll a twenty-sided dice, and return the **herobody()**
            result as well.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [t: herostun(1, 20)] - [t: herobody(1, 20)

            Returns a number that is between ``1`` and ``20`` for the
            herostun roll, and a number between ``0`` and ``2`` for the
            herobody roll.

            Roll five ten-sided dice, and return the **herobody()**
            result as well, using variables.

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
            `herostun() </rptools/wiki/herostun>`__
            For another method of rolling dice, see `Dice
            Expressions </rptools/wiki/Dice_Expressions>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=herobody&oldid=3079"

