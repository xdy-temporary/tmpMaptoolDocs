=======================
json.count - MapToolDoc
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

   .. rubric:: json.count
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

            -  `1 json.count() Function <#json.count.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.count() Function
            :name: json.count-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns the number of occurrences of a value in a `JSON
            Array </rptools/wiki/JSON_Array>`__. If the value does
            not occur in the `JSON Array </rptools/wiki/JSON_Array>`__
            then ``-1`` is returned. The index for the `JSON
            Array </rptools/wiki/JSON_Array>`__

            starts at ``0``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.count(array, value)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.count(array, value, start)]

         **Parameters**

         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            search.
         -  ``value`` - The value to count the occurrences of.
         -  ``start`` - The index to start searching from, if not
            specified it defaults to ``0``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Find the number of occurrences of ``1``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.count("[1,2,3,1,1,3]", 1)]

            Returns ``3``

            Find the number of occurrences of ``1``, starting at index
            ``1``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.count("[1,2,3,1,1,3]", 1, 1)]

            Returns ``2``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.contains() </rptools/wiki/json.contains>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.count&oldid=2511"

