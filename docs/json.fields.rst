.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.fields
   |version=1.3b49
   |description=
   Returns the fields (keys) for a [[JSON_Object|JSON Object]] or the indexes for a [[JSON_Array|JSON Array]] as a string list. The type of the value returned depends on the delimiter parameter. 

   <u>Note</u>: Because [[JSON_Object|JSON Object]]s are unordered, ''json.fields'' will not reflect the order they were set in.

   |usage=
   <source lang="mtmacro" line>
   json.fields(jobj)
   </source>
   <source lang="mtmacro" line>
   json.fields(jobj, delim)
   </source>

   '''Parameters'''
   * {{code|delim}} =
   ** {{code|unspecified}}: a standard [[Macros:string_list|string list]] is returned, with its default {{code|","}} delimiter.
   ** {{code|"json"}}: a [[JSON_Array|JSON Array]] is returned.
   ** {{code|"x"}}: a [[Macros:string_list|string list]] is returned with {{code|"x"}} used as a delimiter.

   |example=
   <source lang="mtmacro" line>
   [h: a=json.fromStrProp("a=1;b=44;c=12")]
   [r: json.fields(a)]
   </source>
   Returns
     b,c,a


   <source lang="mtmacro" line>
   [h: a=json.fromList("a,1,g,4")]
   [r: json.fields(a,";")]
   </source>
   Returns
     0;1;2;3


   <source lang="mtmacro" line>
   [h: a=json.fromStrProp("a=1;b=44;c=12")]
   [r: json.fields(a, "json")]
   </source>
   Returns
     ["a","c","b"]
   }}

`Category:JSON Function <Category:JSON_Function>`__
