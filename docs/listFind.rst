=====================
listFind - MapToolDoc
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

   .. rubric:: listFind
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

         .. rubric:: listFind() Function
            :name: listfind-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the index of the first occurrence of a value in a
            `string list </rptools/wiki/Macros:string_list>`__. If the
            value is not found then -1 is returned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listFind(list, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listFind(list, value, delim)

         If delim is not specified then the default value of ',' is used
         as the value separator in the `string
         list </rptools/wiki/Macros:string_list>`__

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listFind("This, is, a, test", "is")]

            Returns 1

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listFind("This: is: a: test", "a", ":")]

            Returns 2

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listFind("This, is, a, test", "not")]

            Returns -1

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listFind&oldid=1899"

