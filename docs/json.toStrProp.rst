.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.toStrProp
   |version=1.3b49
   |description=
   Creates a [[Macros:string_property_list|string list]] from a [[JSON_Object|json object]]. With the specified delimiter, if a delimiter is not provided then the default value of ';' is used.

   |usage=
   <source lang="mtmacro" line>
   [h: strProp = json.toStrProp(jobj)]
   [h: strProp = json.toStrProp(jobj, delim)]
   </source>

   |example=
   <source lang="mtmacro" line>
     [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.toStrProp(a)]
     [h:a=json.fromList("a,1,g,4")][r:json.toStrProp(a)]
   </source>

   Returns
     a=1;c=12;b=44
     0=a;1=1;2=g;3=4
   }}

`Category:JSON Function <Category:JSON_Function>`__
