.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.merge
   |version=1.3b53
   |description=
   Merges multiple [[JSON_Array|JSON Array]]s or [[JSON_Object|JSON Object]]s.

   For [[JSON_Array|JSON Array]]s the value returned is that of all the [[JSON_Array|JSON Array]]s concatenated together.

   For [[JSON_Object|JSON Object]]s the value returned is a [[JSON_Object|JSON Object]] with all of the keys from all of the [[JSON_Object|JSON Object]]s set, if any key is specified in more than one [[JSON_Object|JSON Object]] then the value for the last specified [[JSON_Object|JSON Object]] is used.

   |usage=
   <source lang="mtmacro" line>
   json.merge(array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.merge(object, object, ...)
   </source>
   '''Parameters'''
   {{param|array|A [[JSON_Array|JSON Array]].}}
   {{param|object|A [[JSON_Object|JSON Object]].}}

   |examples=
   Merge three [[JSON_Array|JSON Array]]s:
   <source lang="mtmacro" line>
   [r: json.merge("[1,2]", "[3,4]", "[1,2]")]
   </source>
   Returns: {{code|[1,2,3,4,1,2]}}

   Merge two [[JSON_Object|JSON Object]]s with no matching keys:
   <source lang="mtmacro" line>
   [r: json.merge("{a:1, b:2}", "{c:10, d:7}")]
   </source>
   Returns: {{code|{"a":1,"b":2,"c":10,"d":7} }}

   Merge three [[JSON_Object|JSON Object]]s with a matching key, {{code|a}}:
   <source lang="mtmacro" line>
   [r: json.merge("{a:1, b:2}", "{c:10, d:7}", "{a:11, z:7}")]
   </source>
   Returns: {{code|{"a":11,"b":2,"c":10,"d":7,"z":7} }}

   |also=
   {{func|json.union}}, {{func|json.intersection}}

   |changes=
   {{change|1.3b54|Fixed bug which allows {{code|json.merge()}} to work correctly with [[JSON_Object|JSON Object]]s.}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
