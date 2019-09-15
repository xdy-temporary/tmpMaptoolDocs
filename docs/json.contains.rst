==========================
json.contains - MapToolDoc
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

   .. rubric:: json.contains
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

            -  `1 json.contains()
               Function <#json.contains.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: json.contains() Function
            :name: json.contains-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns ``true``\ (``1``) if the `JSON
            Object </rptools/wiki/JSON_Object>`__ contains the specified
            key, or if the `JSON Array </rptools/wiki/JSON_Array>`__
            contains the specified value.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.contains(object, key)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.contains(array, value)

         **Parameters**

         -  ``object`` - The `JSON Object </rptools/wiki/JSON_Object>`__
            to test for the key.
         -  ``key`` - The key to check the object for.
         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            test for the value.
         -  ``value`` - The value to check the array for.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Check if the `JSON Object </rptools/wiki/JSON_Object>`__
            ``a`` contains the key ``"b"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:a=json.fromStrProp("a=1;b=44;c=12")]

                  #. .. code-block:: none

                        [json.contains(a,"b")]

            Returns ``true``\ (``1``)

            Check if the `JSON Object </rptools/wiki/JSON_Object>`__
            ``a`` contains the key ``"z"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:a=json.fromStrProp("a=1;b=44;c=12")]

                  #. .. code-block:: none

                        [json.contains(a,"z")]

            Returns ``false``\ (``0``)

            Check if the `JSON Array </rptools/wiki/JSON_Array>`__ ``a``
            contains the value ``"b"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:a=json.fromList("1,b,3,d")]

                  #. .. code-block:: none

                        [json.contains(a,"b")]

            Returns ``true``\ (``1``)

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.type() </rptools/wiki/json.type>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ability for function to work with
               `JSON Arrays </rptools/wiki/JSON_Array>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.contains&oldid=2509"

