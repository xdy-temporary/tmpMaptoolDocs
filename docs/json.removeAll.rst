.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=json.removeAll
   |version=1.3b53
   |description=
   Removes all the keys or values from the first [[JSON_Object|JSON Object]] or [[JSON_Array|JSON Array]] that occur in the following [[JSON_Object|JSON Object]]s or [[JSON_Array|JSON Array]]s.

   |usage=
   <source lang="mtmacro" line>
   json.removeAll(firstArray, array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.removeAll(firstObject, object, object, ...)
   </source>
   '''Parameters'''
   {{param|firstArray|The [[JSON_Array|JSON Array]] to remove the occurrences from.}}
   {{param|array|The [[JSON_Array|JSON Array]]s to get the occurrences from.}}
   {{param|firstObject|The [[JSON_Object|JSON Object]] to remove the occurrences from.}}
   {{param|object|The [[JSON_Object|JSON Object]]s to get the occurrences from.}}

   |also=
   {{func|json.unique}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
