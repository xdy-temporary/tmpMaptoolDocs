=======================
bitwisexor - MapToolDoc
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

   .. rubric:: bitwisexor
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
         from\ `bxor </maptool/index.php?title=bxor&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: bitwisexor() Function
            :name: bitwisexor-function

         .. container:: template_description

            Performs a bitwise 'exlusive or' operation of the number
            arguments by taking the binary representation of each of the
            numbers and performing the logical exclusive or operation on
            each of the bits.
            **Logical " exclusive or" Table**

            ==== ==== ======
            Bit1 Bit2 Result
            0    0    0
            0    1    1
            1    1    0
            ==== ==== ======

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: val = bxor(num, num, ...)]

               #. .. code-block:: none

                     [h: val = bitwisexor(num, num, ...)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bxor(1,0)]

            Returns 1.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bxor(1,1)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bxor(0,0)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bxor(2, 4]

            Returns 6. 2 in binary is 010 and 4 in binary is 100, so a
            bitwise xor of these two values is 110 which is 6 in
            decimal.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bxor(6, 4)]

            Returns 2.

            6 in binary is 110 and 4 in binary is 100, so a bitwise xor
            of these two values is 010 which is 2 in decimal.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bitwisexor&oldid=7409"

