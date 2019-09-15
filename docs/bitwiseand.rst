=======================
bitwiseand - MapToolDoc
=======================

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

   .. rubric:: bitwiseand
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

         .. rubric:: bitwiseand() Function
            :name: bitwiseand-function

         .. container:: template_description

            Performs a bitwise 'and' operation of the {number} arguments
            by taking the binary representation of each of the numbers
            and performing the logical and operation on each of the
            bits.
            **Logical "and" Table**

            ==== ==== ======
            Bit1 Bit2 Result
            0    0    0
            0    1    0
            1    1    1
            ==== ==== ======

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: val = band(num, num, ...)]

               #. .. code-block:: none

                     [h: val = bitwiseand(num, num, ...)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: band(1,0)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: band(1,1)]

            Returns 1.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: band(3, 5]

            Returns 1. 3 in binary is 011 and 5 in binary is 101, the
            bitwise 'and' of these values is 001 in binary which is 1 in
            decimal.

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
         "http://lmwcs.com/maptool/index.php?title=bitwiseand&oldid=4332"

