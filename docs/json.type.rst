.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.type
   |version=1.3b49
   |description=
   Returns a string which contains the type of JSON variable that is passed in.
   Return values are
   * {{code|ARRAY}} - The object is a [[JSON_Array|JSON Array]].
   * {{code|OBJECT}} - The object is a [[JSON_Object|JSON Object]].
   * {{code|UNKNOWN}} - It is neither a [[JSON_Array|JSON Array]] nor [[JSON_Object|JSON Object]].
    

   |usage=
   <source lang="mtmacro" line>
   [h: jarr = json.type(val)]
   </source>

   |examples=
   <source lang="mtmacro" line>
     [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.type(a)]
     [h:a=json.fromList("a,1,g,4")][r:json.type(a)]
     [r:json.type("some thing or other")]
   </source>

   Returns
     OBJECT
     ARRAY
     UNKNOWN
   }}

`Category:JSON Function <Category:JSON_Function>`__
