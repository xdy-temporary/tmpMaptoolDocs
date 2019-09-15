.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.length
   |version=1.3b49
   |description=
   Returns the number of fields in a [[JSON_Object|json object]] or number of elements in a [[JSON_Array|json array]].

   |usage=
   <source lang="mtmacro" line>
   [h: len = json.length(jobj)]
   [h: len = json.length(jarr)]
   </source>

   |example=
   <source lang="mtmacro" line>
     [h:a=json.fromStrProp("a=1;b=44;c=12")] [json.length(a)]
     [h:a=json.fromList("a,1,g,4")][json.length(a)]
   </source>

   Returns
     3
     4
   }}

`Category:JSON Function <Category:JSON_Function>`__
