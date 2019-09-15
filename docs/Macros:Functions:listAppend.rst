=======================
listAppend - MapToolDoc
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

   .. rubric:: listAppend
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
         from\ `Macros:Functions:listAppend </maptool/index.php?title=Macros:Functions:listAppend&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: listAppend() Function
            :name: listappend-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns a `string list <Macros:string_list>`__
            with a value appended to the end of the `string
            list <Macros:string_list>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listAppend(list, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listAppend(list, value, delim)

         If delim is not specified then the default value of ',' is used
         to separate the values in the `string
         list <Macros:string_list>`__

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listAppend("This, is, a", "test")]

            Returns This, is, a, test

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listAppend("This: is: a:", "test", ":")]

            Returns This: is: a: test

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listAppend&oldid=1900"

