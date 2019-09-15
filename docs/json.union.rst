.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.union
   |version=1.3b53
   |description=
   Returns an [[JSON_Array|JSON Array]] with the union of all of the [[JSON_Object|JSON Object]] keys, or [[JSON_Array|JSON Array]] values.  If a value or a key occurs in multiple different objects or arrays, it will only be placed once in the output object or array.

   |usage=
   <source lang="mtmacro" line>
   json.union(array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.union(object, object, ...)
   </source>
   '''Parameters'''
   {{param|array|The [[JSON_Array|JSON Array]]s to union.}}
   {{param|object|The [[JSON_Object|JSON Object]]s to union.}}

   |examples=
   <source lang="mtmacro" line>
     [h: array1 = json.append("",1,2,3,4)]
     [h: array2 = json.append("",3,4,5,6)]
     [r: json.union(array1,array2)]
   </source>

   Returns
    "[1,2,3,4,5,6]"


   |also=
   {{func|json.merge}}, {{func|json.intersection}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
