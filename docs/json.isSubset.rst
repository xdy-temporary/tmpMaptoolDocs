==========================
json.isSubset - MapToolDoc
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

   .. rubric:: json.isSubset
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: json.isSubset() Function
            :name: json.issubset-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns ``true``\ (``1``) if all of the `JSON
            Object <JSON_Object>`__ keys or `JSON
            Array <JSON_Array>`__ values are contained
            within the first `JSON Object <JSON_Object>`__
            or `JSON Array <JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.isSubset(firstArray, array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.isSubset(firstObject, object, object, ...)

         **Parameters**

         -  ``firstArray`` - The `JSON
            Array <JSON_Array>`__ that must contain all of
            the values of the subsequent `JSON
            Arrays <JSON_Array>`__ for this function to
            return ``true``\ (``1``).
         -  ``array`` - A `JSON Array <JSON_Array>`__ with
            values that are tested to be within the ``firstArray``.
         -  ``firstObject`` - The `JSON
            Object <JSON_Object>`__ that must contain all
            of the keys of the subsequent `JSON
            Objects <JSON_Object>`__ for this function to
            return ``true``\ (``1``).
         -  ``object`` - A `JSON Object <JSON_Object>`__
            with keys that are tested to be within the ``firstObject``.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.contains() <json.contains>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.isSubset&oldid=6054"

