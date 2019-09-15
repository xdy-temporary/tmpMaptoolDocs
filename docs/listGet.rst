====================
listGet - MapToolDoc
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

   .. rubric:: listGet
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

         .. rubric:: listGet() Function
            :name: listget-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the value in the `string
            list </rptools/wiki/Macros:string_list>`__ at the specified
            index. The index for a `string
            list </rptools/wiki/Macros:string_list>`__ starts at 0.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listGet(list, index)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listGet(list, index, delim)

         If delim is not specified then the default value of ',' is used
         as the value separator in the `string
         list </rptools/wiki/Macros:string_list>`__

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listGet("This, is, a , test", 2)]

            Returns a

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listGet("This: is: a :test", 1, ":")]

            Returns is

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listGet&oldid=1896"

