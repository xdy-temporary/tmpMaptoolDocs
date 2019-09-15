======================
listCount - MapToolDoc
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

   .. rubric:: listCount
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

         .. rubric:: listCount() Function
            :name: listcount-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the number of items in a `string
            list </rptools/wiki/Macros:string_list>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listCount(list)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listCount(list, delim)

         If delim is not specified then the default value of ',' is used
         as the value separator in the `string
         list </rptools/wiki/Macros:string_list>`__

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listCount("This, is, a, test")]

            Returns 4

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listCount("This: is: a: test",":")]

            Returns 4

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listCount&oldid=1898"

