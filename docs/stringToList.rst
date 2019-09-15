=========================
stringToList - MapToolDoc
=========================

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

   .. rubric:: stringToList
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

         .. rubric:: stringToList() Function
            :name: stringtolist-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Converts a string into a `string
            list <Macros:string_list>`__ using a pattern
            to determine separator between elements. The specified
            delimiter is used to separate the elements in the
            `Macros:string list <Macros:string_list>`__ if
            it is specified, otherwise the default value of "," is used.
            Pattern can be a `regular
            expression <Macros:regular_expression>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     stringToList(str, pattern)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     stringToList(str, pattern, delim)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [stringToList("This is a test", " ")]

                  #. .. code-block:: none

                            [stringToList("1,2,3,4", ",", ":")]

            Returns

            ::

                  This,is,a,test

            1:2:3:4

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=stringToList&oldid=1918"

