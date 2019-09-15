=========================
json.indexOf - MapToolDoc
=========================

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

   .. rubric:: json.indexOf
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

            -  `1 json.indexOf()
               Function <#json.indexOf.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.indexOf() Function
            :name: json.indexof-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns the index of the first occurrence of a value in the
            `JSON Array </rptools/wiki/JSON_Array>`__. If the value does
            not exist in the `JSON Array </rptools/wiki/JSON_Array>`__
            then ``-1`` is returned. All `JSON
            Array </rptools/wiki/JSON_Array>`__ indexes start at ``0``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.indexOf(array, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.indexOf(array, value, start)

         **Parameters**

         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            search.
         -  ``value`` - The value to find the index of in the `JSON
            Array </rptools/wiki/JSON_Array>`__.
         -  ``start`` - The index to start searching from, if not
            specified it defaults to ``0``.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Find the index of the first occurrence of ``1``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.indexOf("[1,2,3,1,1,3]", 1)]

            Returns: ``0``

            Find the index of the first occurrence of ``1``, starting at
            index ``1``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.count("[1,2,3,1,1,3]", 1, 1)]

            Returns: ``3``

            Find the index of the first occurrence of ``2``, starting at
            index ``2``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.count("[1,2,3,1,1,3]", 2, 2)]

            Returns: ``-1``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.count() </rptools/wiki/json.count>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.indexOf&oldid=2512"

