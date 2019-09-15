=====================
json.set - MapToolDoc
=====================

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

   .. rubric:: json.set
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

            -  `1 json.set() Function <#json.set.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.set() Function
            :name: json.set-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Sets the value in at the specified index in a `JSON
            Array </rptools/wiki/JSON_Array>`__ or for the specified key
            in a `JSON Object </rptools/wiki/JSON_Object>`__. You can
            use an empty string (``""``) to represent a new `JSON
            Array </rptools/wiki/JSON_Array>`__ or `JSON
            Object </rptools/wiki/JSON_Object>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     newarr=json.set(jarr, [])

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     newarr=json.set(jarr, index, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     newarr=json.set(jarr, index, value, ..., ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     newobj=json.set(jobj, key, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     newobj=json.set(jobj, key, value, ..., ...)

         **Parameters**

         -  ``jarr`` - The `JSON Array </rptools/wiki/JSON_Array>`__
            that has an index's value set.
         -  ``index`` - The numeric index which has its value set.
         -  ``jobj`` - The `JSON Object </rptools/wiki/JSON_Object>`__
            that has a key's value set.
         -  ``key`` - The named key which has its value set.
         -  ``value`` - The content that is set to the ``index`` or
            ``key``.

         **Note:** The ``index`` and ``value`` parameters or ``key`` and
         ``value`` parameters can be repeated in pairs.

         **Note:** ``newarr`` or ``newobj`` can be equal to ``jarr`` or
         ``jobj``. In this case, the object/array will simply be
         updated.

         **Note:** The word "class" is a reserved word in JavaScript; it
         is therefore not possible to create a JSON object containing a
         *key* named "Class," "class," or any mix of upper- and
         lower-case. MapTool will ignore any instructions to set a JSON
         object key with that name.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [json.set("{}", "a", 5)]

                  #. .. code-block:: none

                          [json.set("", "a", 5, "b", 8)]

                  #. .. code-block:: none

                          [json.set(json.fromList("1,3"), 0, 8)]

            Returns

            ::

                {"a":5}
                {"a":5, "b":8}
                [8, 3]

            To save the new value in the `JSON
            Array </rptools/wiki/JSON_Array>`__ or `JSON
            Object </rptools/wiki/JSON_Object>`__ so that you can
            reference it later in a macro, you must set the array equal
            to the result of json.set().

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                           [myArray = json.append("", 1, 2, 3)]

                  #. .. code-block:: none

                           [myArray = json.set(myArray, 0, 5)]

                  #. .. code-block:: none

                           [myArray]

            Returns

            ::

                 [1,2,3] 
                 [5,2,3] 

            [5,2,3]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.get() </rptools/wiki/json.get>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.set&oldid=4828"

