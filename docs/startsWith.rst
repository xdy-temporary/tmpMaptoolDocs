=======================
startsWith - MapToolDoc
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

   .. rubric:: startsWith
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

         .. rubric:: startsWith() Function
            :name: startswith-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns ``true``\ (``1``) if the first parameter starts with
            the contents of the second parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: result = startsWith(string, substring)]

         Returns ``true``\ (``1``) if the string starts with a certain
         substring and ``false``\ (``0``) if not.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: startsWith("Test", "T")]

                  #. .. code-block:: none

                        [r: startsWith("Test", "Te")]

                  #. .. code-block:: none

                        [r: startsWith("Test", "Tez")]

            **Returns**

            ::

                 1
                 1
                 0

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=startsWith&oldid=7138"

