========================
listReplace - MapToolDoc
========================

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

   .. rubric:: listReplace
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

         .. rubric:: listReplace() Function
            :name: listreplace-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Replaces the element at the specified index of a `String
            List </rptools/wiki/String_List>`__ with a new value. If a
            delimiter is not specified then the default value of ``","``
            is used. The index for lists starts at ``0``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listReplace(list, index, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listReplace(list, index, value, delim)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Simple example:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listReplace("This, isnt, a , test", 1, "is")]

            Returns ``This, is, a, Test``

            **Example using a**\ `String
            List </rptools/wiki/String_List>`__\ **with a non-default
            delimiter:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listReplace("This: isnt: a: test", 1, "is", ":")]

            Returns ``This: is: a: test``

            **Example using a**\ `String
            List </rptools/wiki/String_List>`__\ **stored in a
            variable:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: ListVar = "This, is, a, great, test"]

                  #. .. code-block:: none

                        [h: ListVar = listReplace(ListVar, 3, "silly")]

                  #. .. code-block:: none

                        [r: ListVar]

            Returns: ``This, is, a, silly, test``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listReplace&oldid=3628"

