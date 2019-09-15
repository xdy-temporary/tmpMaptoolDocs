=======================
listInsert - MapToolDoc
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

   .. rubric:: listInsert
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

         .. rubric:: listInsert() Function
            :name: listinsert-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Inserts a value into the `string
            list <Macros:string_list>`__ at the specified
            index. If a delimiter is not specified then the default
            value of ',' is used. The index for lists starts at 0

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listInsert(list, index, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listInsert(list, index, value, delim)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listInsert("This, a , test", 1, "is")]

            Returns This, is, a, Test

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listInsert("This: a: test", 1, "is", ":")]

            Returns This: is: a: test

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listInsert&oldid=1901"

