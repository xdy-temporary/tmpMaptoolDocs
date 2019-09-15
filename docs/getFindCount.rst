=========================
getFindCount - MapToolDoc
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

   .. rubric:: getFindCount
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

         .. rubric:: getFindCount() Function
            :name: getfindcount-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the number of times that
            `strfind() </rptools/wiki/strfind>`__ was able to match the
            input string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getFindCount(id)

         The id is the id value returned by
         `strfind() </rptools/wiki/Macros:Functions:strfind>`__.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = strfind("this is a test", "(\\S+)\\s+(\\S+)\\s*")]

                  #. .. code-block:: none

                        [r: getFindCount(id)]

            Returns 2.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getFindCount&oldid=1932"

