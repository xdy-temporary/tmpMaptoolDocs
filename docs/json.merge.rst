=======================
json.merge - MapToolDoc
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

   .. rubric:: json.merge
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

            -  `1 json.merge() Function <#json.merge.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: json.merge() Function
            :name: json.merge-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Merges multiple `JSON Arrays </rptools/wiki/JSON_Array>`__
            or `JSON Objects </rptools/wiki/JSON_Object>`__.
            For `JSON Arrays </rptools/wiki/JSON_Array>`__ the value
            returned is that of all the `JSON
            Arrays </rptools/wiki/JSON_Array>`__ concatenated together.

            For `JSON Objects </rptools/wiki/JSON_Object>`__ the value
            returned is a `JSON Object </rptools/wiki/JSON_Object>`__
            with all of the keys from all of the `JSON
            Objects </rptools/wiki/JSON_Object>`__ set, if any key is
            specified in more than one `JSON
            Object </rptools/wiki/JSON_Object>`__ then the value for the
            last specified `JSON Object </rptools/wiki/JSON_Object>`__
            is used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.merge(array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.merge(object, object, ...)

         **Parameters**

         -  ``array`` - A `JSON Array </rptools/wiki/JSON_Array>`__.
         -  ``object`` - A `JSON Object </rptools/wiki/JSON_Object>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Merge three `JSON Arrays </rptools/wiki/JSON_Array>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.merge("[1,2]", "[3,4]", "[1,2]")]

            Returns: ``[1,2,3,4,1,2]``

            Merge two `JSON Objects </rptools/wiki/JSON_Object>`__ with
            no matching keys:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.merge("{a:1, b:2}", "{c:10, d:7}")]

            Returns: ``{"a":1,"b":2,"c":10,"d":7}``

            Merge three `JSON Objects </rptools/wiki/JSON_Object>`__
            with a matching key, ``a``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.merge("{a:1, b:2}", "{c:10, d:7}", "{a:11, z:7}")]

            Returns: ``{"a":11,"b":2,"c":10,"d":7,"z":7}``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.union() </rptools/wiki/json.union>`__,
            `json.intersection() </rptools/wiki/json.intersection>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b54** - Fixed bug which allows ``json.merge()`` to
               work correctly with `JSON
               Objects </rptools/wiki/JSON_Object>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.merge&oldid=6193"

