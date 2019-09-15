.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.toList
   |version=1.3b49
   |description=
   Creates a [[Macros:string_list|string list]] from a [[JSON_Array|JSON Array]]. If the delimiter is not specified then the default value of ',' is used.

   |usage=
   <source lang="mtmacro" line>
   [h: jarr = json.toList(jarr)]
   [h: jarr = json.toList(jarr, delim)]
   </source>

   |examples=
   <source lang="mtmacro" line>
     [h:a=json.fromList("a,1,g,4")]
     [json.toList(a)]
   </source>

   Returns
        a,1,g,4
   }}

`Category:JSON Function <Category:JSON_Function>`__
