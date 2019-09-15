===========================
json.removeAll - MapToolDoc
===========================

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

   .. rubric:: json.removeAll
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

         .. rubric:: json.removeAll() Function
            :name: json.removeall-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Removes all the keys or values from the first `JSON
            Object </rptools/wiki/JSON_Object>`__ or `JSON
            Array </rptools/wiki/JSON_Array>`__ that occur in the
            following `JSON Objects </rptools/wiki/JSON_Object>`__ or
            `JSON Arrays </rptools/wiki/JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.removeAll(firstArray, array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.removeAll(firstObject, object, object, ...)

         **Parameters**

         -  ``firstArray`` - The `JSON
            Array </rptools/wiki/JSON_Array>`__ to remove the
            occurrences from.
         -  ``array`` - The `JSON Arrays </rptools/wiki/JSON_Array>`__
            to get the occurrences from.
         -  ``firstObject`` - The `JSON
            Object </rptools/wiki/JSON_Object>`__ to remove the
            occurrences from.
         -  ``object`` - The `JSON
            Objects </rptools/wiki/JSON_Object>`__ to get the
            occurrences from.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.unique() </rptools/wiki/json.unique>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.removeAll&oldid=2515"

