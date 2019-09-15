==========================
getGroupStart - MapToolDoc
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

   .. rubric:: getGroupStart
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

         .. rubric:: getGroupStart() Function
            :name: getgroupstart-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the start index of the specified capture group for
            the specified match that was found using
            `strfind() <strfind>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getGroupStart(id, match, group)

         Where

         -  id is the id returned by
            `strfind() <strfind>`__
         -  match is the number of the match found by
            `strfind() <strfind>`__
         -  group is the number of the capture group found by
            `strfind() <strfind>`__

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]

                  #. .. code-block:: none

                        match 1, group 1 start = [getGroupStart(id, 1, 1)]<br>

                  #. .. code-block:: none

                        match 1, group 2 start = [getGroupStart(id, 1, 2)]<br>

                  #. .. code-block:: none

                        match 2, group 1 start = [getGroupStart(id, 2, 1)]<br>

                  #. .. code:: de2

                        match 2, group 2 start = [getGroupStart(id, 2, 2)]<br>

            Returns

            ::

               match 1, group 1 start = 0 
               match 1, group 2 start = 5 
               match 2, group 1 start = 8 
               match 2, group 2 start = 10 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getGroupStart&oldid=1935"

