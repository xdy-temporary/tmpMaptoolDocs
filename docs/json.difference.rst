============================
json.difference - MapToolDoc
============================

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

   .. rubric:: json.difference
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 json.difference()
               Function <#json.difference.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.difference() Function
            :name: json.difference-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns an array with the differences of all of the `JSON
            Object </rptools/wiki/JSON_Object>`__ keys, or `JSON
            Array </rptools/wiki/JSON_Array>`__ values. Output contains
            keys or values which exist in the first parameter, but do
            not exist in any others.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.difference(array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.difference(object, object, ...)

         **Parameter**

         -  ``array`` - A `JSON Array </rptools/wiki/JSON_Array>`__ to
            get the difference of.
         -  ``object`` - A `JSON Object </rptools/wiki/JSON_Object>`__
            to get the difference of.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            So per example:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.difference(array2, array1)]

            will result in ``array2`` from which all elements that are
            found in ``array1`` are removed.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.union() </rptools/wiki/json.union>`__,
            `json.merge() </rptools/wiki/json.merge>`__,

            `json.intersection() </rptools/wiki/json.intersection>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.difference&oldid=6194"

