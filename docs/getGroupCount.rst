==========================
getGroupCount - MapToolDoc
==========================

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

   .. rubric:: getGroupCount
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

         .. rubric:: getGroupCount() Function
            :name: getgroupcount-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the number of capture groups for the match performed
            by `strfind() </rptools/wiki/strfind>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: text = getGroupCount(id)]

         id is the id returned by `strfind() </rptools/wiki/strfind>`__

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]

                  #. .. code-block:: none

                        [r: getGroupCount(id)]

            Returns 2.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getGroupCount&oldid=1933"

