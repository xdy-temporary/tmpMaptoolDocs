========================
json.append - MapToolDoc
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

   .. rubric:: json.append
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

         .. rubric:: json.append() Function
            :name: json.append-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Appends values to the end of a `JSON
            Array </rptools/wiki/JSON_Array>`__. An empty string ("")
            can be used to represent an empty `JSON
            Array </rptools/wiki/JSON_Array>`__ to append the values to.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: jarr = json.append(jarr, value, ...)]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")][r: json.append(a, 55)]

                  #. .. code-block:: none

                          [r: json.append("", 1, 5, 8, 33)]

            Returns

            ::

                 ["a",1,"g",4,55]

            [1,5,8,33]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.append&oldid=2921"

