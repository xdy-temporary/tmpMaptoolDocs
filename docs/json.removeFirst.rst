=============================
json.removeFirst - MapToolDoc
=============================

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

   .. rubric:: json.removeFirst
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 json.removeFirst()
               Function <#json.removeFirst.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.removeFirst() Function
            :name: json.removefirst-function

         .. container:: template_version

            • **Introduced in version 1.4.0.3**

         .. container:: template_description

            Is similar to
            `json.difference() <json.difference>`__ but
            will only remove the first occurrence of a match.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.removeFirst(array1, array2)

         **Parameters**

         -  ``array1`` - A JSON array.
         -  ``array2`` - A JSON array.

         Compares the two arrays and removes the first element from the
         first array matching an element in the second.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.removeFirst('[2,2,4,5,6,6,4]', '[2,6]')]

            **Outputs:**

            ::

                 [2,4,5,6,4]

            Difference between **json.removeFirst()** and
            `json.difference() <json.difference>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: a1 = '[1,2,2,2,3,3,4,5,6,6]']

                  #. .. code-block:: none

                        [h: a2 = '[2,4,6]']

                  #. .. code-block:: none

                        [r: json.difference(a1,a2)]

                  #. .. code-block:: none

                        <!-- a1 has been modified - reset -->

                  #. .. code:: de2

                        [h: a1 = '[1,2,2,2,3,3,4,5,6,6]']

                  #. .. code-block:: none

                        [r: json.removeFirst(a1,a2)]

            **Outputs:**

            ::

                 [1,3,5]
                 [1,2,2,3,3,5,6]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to JSON
            Datatypes <Introduction_to_JSON_Datatypes>`__
            , `json.difference() <json.difference>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.removeFirst&oldid=7135"

