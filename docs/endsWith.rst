=====================
endsWith - MapToolDoc
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

   .. rubric:: endsWith
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

         .. rubric:: endsWith() Function
            :name: endswith-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns 1 if the string ends with a certain sub string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: result = endsWith(str, substr)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: endsWith("Test", "t")]

                  #. .. code-block:: none

                        [r: endsWith("Test", "st")]

                  #. .. code-block:: none

                        [r: endsWith("Test", "z")]

            Returns

            ::

                  1
                  1

            0

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=endsWith&oldid=1145"

