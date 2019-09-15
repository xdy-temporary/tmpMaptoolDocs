=====================
listSort - MapToolDoc
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

   .. rubric:: listSort
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: listSort() Function
            :name: listsort-function

         .. container:: template_description

            Returns a sorted list.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [listSort(list, sortType)]

         The sortType determines the type of sort to use. If sortType is
         "A", normal alphabetic sorting is used, and "Monster11" comes
         before "Monster3". (Default behavior) If sortType is "N", the
         first number in each entry is effectively padded to 4 digits,
         so that "Monster3" comes before "Monster11". The sortType can
         have a second character of "+" or "-" to specify an ascending
         or descending sort.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: UnsortedList = "Monster11,Monster3,Monster12,Monster66,Monster87,Monster71"]

                  #. .. code-block:: none

                        [h: SortedList = listSort(UnsortedList,'N')]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        Unsorted list: [r: UnsortedList]<br>

                  #. .. code:: de2

                        Sorted list: [r: SortedList]

            Returns:

            ::

                Unsorted list: Monster11,Monster3,Monster12,Monster66,Monster87,Monster71

            Sorted list: Monster3, Monster11, Monster12, Monster66,
            Monster71, Monster87

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listSort&oldid=2191"

