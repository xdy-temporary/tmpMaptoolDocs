=======================
json.rolls - MapToolDoc
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

   .. rubric:: json.rolls
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

         .. rubric:: json.rolls() Function
            :name: json.rolls-function

         .. container:: template_version

            • **Introduced in version 1.4.0.5**

         .. container:: template_description

            Rolls the dice expression the requested number of times and
            returns a JSON Array with the result.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.rolls(roll, dim1)

               #. .. code-block:: none

                     json.rolls(roll, dim1, dim2)

         **Parameters**

         -  ``roll`` - A string containing a dice roll expression.
         -  ``dim1`` - The dimension of the returned array.
         -  ``dim2`` - Optional: The second dimension for a two
            dimensional array.

         This function takes 2 or 3 parameters and returns a json array
         json.rolls(roll, dim1, dim2) => returns a json array with the
         rolls performed

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {json.rolls("3d6", 6)} => [ 11, 7, 15, 8, 10, 13 ]

         *Example:* The three parameter version returns a two
         dimensional array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {json.rolls("3d6", 6, 4)} => [ [ 11, 13, 11, 13 ], [ 8, 11, 17, 10 ], [ 8, 11, 14, 11 ], [ 6, 8, 13, 6 ], [ 6, 11, 8, 10 ], [ 10, 7, 17, 11 ] ]

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to JSON
            Datatypes </rptools/wiki/Introduction_to_JSON_Datatypes>`__
            , `json.objrolls() </rptools/wiki/json.objrolls>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.rolls&oldid=7127"

