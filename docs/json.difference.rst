.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=json.difference
   |version=1.3b53
   |description=
   Returns an array with the differences of all of the [[JSON_Object|JSON Object]] keys, or [[JSON_Array|JSON Array]] values.  Output contains keys or values which exist in the first parameter, but do not exist in any others.

   |usage=
   <source lang="mtmacro" line>
   json.difference(array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.difference(object, object, ...)
   </source>
   '''Parameter'''
   {{param|array|A [[JSON_Array|JSON Array]] to get the difference of.}}
   {{param|object|A [[JSON_Object|JSON Object]] to get the difference of.}}
   |example=
   So per example:
   <source lang="mtmacro" line>
   [json.difference(array2, array1)]
   </source>
   will result in {{code|array2}} from which all elements that are found in {{code|array1}} are removed. 

   |also=
   {{func|json.union}}, 
   {{func|json.merge}},
   {{func|json.intersection}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
