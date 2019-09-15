=======================
bitwisenot - MapToolDoc
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

   .. rubric:: bitwisenot
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

         .. rubric:: bitwisenot() Function
            :name: bitwisenot-function

         .. container:: template_description

            Performs a bitwise 'not' operation of the {number}. A
            bitwise not is performed by taking the binary representation
            of the {number} and performing a logical 'not' operation on
            each of these bits.
            **Logical "not" Table**

            === ======
            Bit Result
            0   1
            1   0
            === ======

            | 
            | Unfortunately its not quite as simple as the table above
              makes it appear since number are a string of 32 (or more
              bits) so a 1 in binary is actually a
              00000000000000000000000000000001 and a 0 is actually a
              00000000000000000000000000000000 so the table is now.

            ::

                      bnot of binary 00000000000000000000000000000000
                              is             11111111111111111111111111111111
                      which is -1 in decimal

            ::

                      bnot of binary 00000000000000000000000000000001 
                      is             11111111111111111111111111111110
                      which is -2 in decimal

            If you are unsure why the results are negative then you can
            get more information by reading
            `Twos_complement <http://en.wikipedia.org/wiki/Twos_complement>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: val = bnot(num)]

               #. .. code-block:: none

                     [h: val = bitwisenot(num)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [bnot(1)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bnot(1)]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: bnot(12]

            Returns -13.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bitwisenot&oldid=1081"

