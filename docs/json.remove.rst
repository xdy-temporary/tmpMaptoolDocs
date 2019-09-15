.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.remove
   |version=1.3b49
   |description=
   Removes a field from a [[JSON_Object|JSON Object]], or the value at the specified index from a [[JSON_Array|JSON Array]].

   |usage=
   <source lang="mtmacro" line>
   [h: jarr = json.remove(jarr, index)]
   [h: jarr = json.remove(jobj, key)]
   </source>

   |examples=
   <source lang="mtmacro" line>
     [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.remove(a, "c")]
     [h:a=json.fromList("a,1,g,4")][r:json.remove(a,3)]
   </source>

   Returns
     {"a":1,"b":44}
     ["a",1,"g"]
   }}

`Category:JSON Function <Category:JSON_Function>`__
