======================
json.sort - MapToolDoc
======================

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

   .. rubric:: json.sort
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

         .. rubric:: json.sort() Function
            :name: json.sort-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Used to sort JSON arrays. If the array contains only
            numbers, they are sorted numerically; otherwise, the values
            are sorted as strings alphabetically.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array, direction)

         If you have a `JSON Array <JSON_Array>`__ that
         contains `JSON Objects <JSON_Object>`__

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.sort(array, direction, key1, ..., keyN)

         **Parameters**

         -  ``array`` - The JSON array to sort.
         -  ``direction`` - Defaults to ``"ascending"``, acceptable
            values:

            -  ``"ascending"``
            -  ``"descending"``
            -  ``"ascend"``
            -  ``"descend"``
            -  ``"asc"``
            -  ``"desc"``
            -  ``"a"``
            -  ``"d"``

         -  ``key1, ..., keyN`` - The keys in the `JSON
            Objects <JSON_Object>`__ contained within the
            `JSON Array <JSON_Array>`__ used for sorting.
            All `JSON Objects <JSON_Object>`__ must
            contain these fields.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Sorting a `JSON Array <JSON_Array>`__
            containing numbers.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("[1,4,5,6,2,1,9,20,1]")]

            Produces ``[1,1,1,2,4,5,6,9,20]``

            Sorting a `JSON Array <JSON_Array>`__
            containing strings.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("['Hero', 'Dragon', 'Elf', 'Wolf', 'Mage', 'Eagle', 'Troll']")]

            Produces
            ``["Dragon","Eagle","Elf","Hero","Mage","Troll","Wolf"]``

            Sorting a mixture of numbers and strings (all will be
            treated as string).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.sort("['Hero', 3, 'Elf', 'Wolf', 100, 'Eagle', 'Troll']")]

            Produces ``[100,3,"Eagle","Elf","Hero","Troll","Wolf"]``

            Sorting objects by a single string key

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "name")]

            Produces

            ``[{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Mage","HP":20},{"name":"Troll","HP":15},{"name":"Wolf","HP":5}]``

            Sorting objects by a single numeric key

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "HP")]

            Produces

            ``[{"name":"Wolf","HP":5},{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]``

            Sorting objects by a two keys, first HP then Name.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:vals = '[ {name:"Hero", HP:10}, 

                  #. .. code-block:: none

                                     {name:"Wolf", HP:5}, 

                  #. .. code-block:: none

                                     {name:"Mage", HP:20}, 

                  #. .. code-block:: none

                                     {name:"Troll", HP:15}, 

                  #. .. code:: de2

                                     {name:"Eagle", HP:5} ]'] 

                  #. .. code-block:: none

                        [json.sort(vals, "a", "HP", "name")]

            Produces

            ``[{"name":"Eagle","HP":5},{"name":"Wolf","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.sort&oldid=7128"

