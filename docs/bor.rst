======================
bitwiseor - MapToolDoc
======================

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

   .. rubric:: bitwiseor
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
         from\ `bor </maptool/index.php?title=bor&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: bitwiseor() Function
            :name: bitwiseor-function

         .. container:: template_description

            Performs a bitwise 'or' operation of the number arguments by
            taking the binary representation of each of the numbers and
            performing the logical or operation on each of the bits.
            **Logical "or" Table**

            ==== ==== ======
            Bit1 Bit2 Result
            0    0    0
            0    1    1
            1    1    1
            ==== ==== ======

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: val = bor(num, num, ...)]

               #. .. code-block:: none

                     [h: val = btwiseor(num, num, ...)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bor(1,0)]

            Returns 1.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bor(1,1)]

            Returns 1.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bor(0,0)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bor(2, 4]

            Returns 6. 2 in binary is 010 and 4 in binary is 100, so a
            bitwise or of these two values is 110 which is 6 in decimal.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: band(20, 12)]

            Returns 4.

            20 in binary is 10100 and 12 in binary is 01100, the bitwise
            'and' of these values is 00100 in binary which is 4 in
            decimal.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bitwiseor&oldid=1086"

