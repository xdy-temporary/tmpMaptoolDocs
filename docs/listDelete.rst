=======================
listDelete - MapToolDoc
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

   .. rubric:: listDelete
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

         .. rubric:: listDelete() Function
            :name: listdelete-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns a `string list </rptools/wiki/Macros:string_list>`__
            with the specified item deleted from it. The index for the
            `string list </rptools/wiki/Macros:string_list>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listDelete(list, index)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listDelete(list, index, delim)

         If delim is not specified then the default value of ',' is used
         as the value separator in the `string
         list </rptools/wiki/Macros:string_list>`__

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listDelete("This, is, a, test", 1)]

            Returns This, a, test

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listDelete&oldid=1897"

