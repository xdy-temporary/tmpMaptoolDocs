===================
median - MapToolDoc
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

   .. rubric:: median
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

         .. rubric:: median() Function
            :name: median-function

         .. container:: template_description

            Returns the `Median <http://en.wikipedia.org/wiki/Median>`__
            of the numbers passed in. The median value is the value
            where half the numbers in the list are higher or equal to it
            and the other half are lower or equal to it. The median is
            calculated by sorting the list of numbers and picking the
            middle number if the list has an odd amount or averaging the
            two in the middle if there is an even amount.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: av = median(num, num, ...)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [r: median(3,6,2,2)]   

                  #. .. code-block:: none

                            [r: median(12, 23, 3, 102, 1)]

            Returns

            ::

                  2.5

            12

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=median&oldid=1598"

