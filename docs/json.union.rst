=======================
json.union - MapToolDoc
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

   .. rubric:: json.union
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

            -  `1 json.union() Function <#json.union.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.union() Function
            :name: json.union-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns an `JSON Array </rptools/wiki/JSON_Array>`__ with
            the union of all of the `JSON
            Object </rptools/wiki/JSON_Object>`__ keys, or `JSON
            Array </rptools/wiki/JSON_Array>`__ values. If a value or a
            key occurs in multiple different objects or arrays, it will
            only be placed once in the output object or array.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.union(array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.union(object, object, ...)

         **Parameters**

         -  ``array`` - The `JSON Arrays </rptools/wiki/JSON_Array>`__
            to union.
         -  ``object`` - The `JSON
            Objects </rptools/wiki/JSON_Object>`__ to union.

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

                          [r: json.union(array1,array2)]

            Returns

            "[1,2,3,4,5,6]"

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.merge() </rptools/wiki/json.merge>`__,
            `json.intersection() </rptools/wiki/json.intersection>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.union&oldid=6192"

