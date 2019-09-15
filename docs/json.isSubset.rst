.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=json.isSubset
   |version=1.3b53
   |description=
   Returns {{true}} if all of the [[JSON_Object|JSON Object]] keys or [[JSON_Array|JSON Array]] values are contained within the first [[JSON_Object|JSON Object]] or [[JSON_Array|JSON Array]].

   |usage=
   <source lang="mtmacro" line>
   json.isSubset(firstArray, array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.isSubset(firstObject, object, object, ...)
   </source>
   '''Parameters'''
   {{param|firstArray|The [[JSON_Array|JSON Array]] that must contain all of the values of the subsequent [[JSON_Array|JSON Array]]s for this function to return {{true}}.}}
   {{param|array|A [[JSON_Array|JSON Array]] with values that are tested to be within the {{code|firstArray}}. }}
   {{param|firstObject|The [[JSON_Object|JSON Object]] that must contain all of the keys of the subsequent [[JSON_Object|JSON Object]]s for this function to return {{true}}.}}
   {{param|object|A [[JSON_Object|JSON Object]] with keys that are tested to be within the {{code|firstObject}}.}}

   |also=
   {{func|json.contains}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
