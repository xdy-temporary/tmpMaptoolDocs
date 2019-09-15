==============================
json.intersection - MapToolDoc
==============================

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

   .. rubric:: json.intersection
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

            -  `1 json.intersection()
               Function <#json.intersection.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.intersection() Function
            :name: json.intersection-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns a `JSON Array <JSON_Array>`__ with the
            intersection of all of the `JSON
            Object <JSON_Object>`__ keys or `JSON
            Array <JSON_Array>`__ values. A value or key
            only appears in the output if it exists in all input arrays
            or objects. This function is useful for removing Token IDs
            from a saved list which have been deleted from the map by
            eliminating them using this function, the saved array and
            `getTokens() <getTokens>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.intersection(array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.intersection(object, object, ...)

         **Parameters**

         -  ``array`` - A `JSON Array <JSON_Array>`__ used
            in the intersection.
         -  ``object`` - A `JSON Object <JSON_Object>`__
            used in the intersection.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h: array1 = json.append("",1,2,3,4)]

                  #. .. code-block:: none

                          [h: array2 = json.append("",3,4,5,6)]

                  #. .. code-block:: none

                          [r: json.intersection(array1,array2)]

            Returns:

            ::

               "[3,4]"

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h: arrayOfSelectedNames = getSelectedNames("json")]

                  #. .. code-block:: none

                          [h: arrayOfNamesOnMap = getTokenNames("json")]

                  #. .. code-block:: none

                          [r: json.intersection(arrayOfSelectedNames,arrayOfNamesOnMap)]

            Input:

            ::

               arrayOfSelectedNames = ["Alexander","Josh"]
               arrayOfNamesOnMap = ["Kevin","Josh","Alexander"]

            Returns:

            ["Alexander","Josh"]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.difference() <json.difference>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.intersection&oldid=6191"

