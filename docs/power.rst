==================
power - MapToolDoc
==================

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

   .. rubric:: power
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

            -  `1 power() Function <#power.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: power() Function
            :name: power-function

         .. container:: template_version

            • **Introduced in version 1.3b36**

         .. container:: template_description

            Returns a ``number`` raised to the power of ``2``, or raised
            to a specific *exponent*.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     power(num)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     power(num, exp)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     pow(num)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     pow(num, exp)

         **Parameters**

         -  ``num`` - the *base number* used to perform the operation.
         -  ``exp`` - the *exponent* used in the operation.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:** Use ``power()`` to raise ``5`` to the power
            of ``2``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: power(5)]

            **Returns:** ``25``

            **Example 2:** Use ``pow()`` to raise ``5`` to the power of
            ``3``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: pow(5, 3)]

            **Returns:** ``125``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Exponentiation <http://en.wikipedia.org/wiki/Exponentiation>`__,
            `ln() <ln>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=power&oldid=1813"

