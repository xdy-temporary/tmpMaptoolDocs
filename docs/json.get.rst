=====================
json.get - MapToolDoc
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

   .. rubric:: json.get
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

            -  `1 json.get() Function <#json.get.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: json.get() Function
            :name: json.get-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns the value in a `JSON
            Array <JSON_Array>`__ at the specified index,
            returns a slice of a `JSON
            Array <JSON_Array>`__ from the specified
            indexes, or returns the value from `JSON
            Object <JSON_Object>`__ for the specified key.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(array, index)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(array, start, end)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(object, key, key, ...)

         **Parameters**

         -  ``array`` - The `JSON Array <JSON_Array>`__ to
            retrieve the element from.
         -  ``index`` - The numerical index of the element you want
            returned.
         -  ``start`` - The starting index of the element you wish the
            slice to begin at.
         -  ``end`` - The ending index of the element you wish the slice
            to end at.
         -  ``object`` - The `JSON Object <JSON_Object>`__
            to retrieve the element from.
         -  ``key`` - The name of a field that should be returned. This
            parameter can exist more than once, if it does then a `JSON
            Object <JSON_Object>`__ is returned with all
            the specified elements.

         When extracting slices: Negative numbers can be used as the
         offsets from the end of the array, ``-1`` is the last element
         in the array, ``-2`` is the second to last, and so on. If the
         ``end`` index is smaller than the ``start`` index then the
         array slice is returned in reverse. This does not work for
         single indices, so if you want to retrieve a single index, say
         the last one in an array, you do that like this:
         json.get(array, -1,-1). This way you take a *slice* of 1 index.
         To get the last element you thus need to do:
         json.get(json.get(array, -1,-1),0) as you get a *slice* and you
         want an *element*.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          a) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b")] <br>

                  #. .. code-block:: none

                          b) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "XX")] <br>

                  #. .. code-block:: none

                          c) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "cat", "a")] <br>

                  #. .. code-block:: none

                          d) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b", "XX")] <br>

                  #. .. code:: de2

                          e) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1)] <br>

                  #. .. code-block:: none

                          f) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2)] <br>

                  #. .. code-block:: none

                          g) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1, 2)] <br>

                  #. .. code-block:: none

                          h) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 0, -1)] <br>

                  #. .. code-block:: none

                          i) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2, 0)] <br> 

                  #. .. code:: de2

                          j) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1, 0)] <br>

                  #. .. code-block:: none

                          ERROR a) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1)] <br>

                  #. .. code-block:: none

                          ERROR b) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 3)] <br>

            Returns

            ::

                a) 44 -- a value
                b)    -- empty string "", as XX does not exist
                c) {"cat":"meow","a":1} -- a JSON object
                d) {"b":44,"XX":""} -- a JSON object
                e) 44 -- a value
                f) meow -- a value
                g) [1,44,"meow"] -- an array slice of 0..2  
                h) ["meow",44] -- an array slice from 2..1 
                i) [1,44,"meow"] -- an array slice from 0..end
                j) ["meow",44] -- an array slice from end..1

            ::

                ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, can't use negatives with a single index param (works OK with slices). 

            ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, the
            last valid index is 2

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ability to return `JSON
               Array <JSON_Array>`__ slices.
            -  **1.3b51** - Added ability to return `JSON
               Objects <JSON_Object>`__ of select fields
               from other `JSON Objects <JSON_Object>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.get&oldid=6848"

