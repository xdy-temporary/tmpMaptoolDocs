====================
matches - MapToolDoc
====================

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

   .. rubric:: matches
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

         .. rubric:: matches() Function
            :name: matches-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns 1 if a string matches pattern or 0 if it does not.
            The pattern can be a `regular
            expression </rptools/wiki/Macros:regular_expression>`__.
            Matches performs a while string comparison, so the pattern
            must match the whole of the input string and not only part
            of it.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     matches(str, pattern)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [r: matches("This is a test", "test")]

                  #. .. code-block:: none

                            [r: matches("test", "test")]

                  #. .. code-block:: none

                            [r: matches("This is a test", ".*test")]

            Returns

            ::

                  0
                  1

            1

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=matches&oldid=1927"

