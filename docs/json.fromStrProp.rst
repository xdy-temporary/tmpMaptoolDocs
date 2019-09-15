.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.fromStrProp
   |version=1.3b49
   |description=
   Creates a [[JSON_Object|json object]] from a [[Macros:string_property_list|string property list]]. 

   |usage=
   <source lang="mtmacro" line>
   json.fromStrProp(propList)
   json.fromStrProp(propList,delim)
   </source>
   '''Parameters'''
   {{param|propList|String property list to extract data from.}} 
   {{param|delim|Delimiter between fields (default is {{code|";"}}).}}

   |example=
   <source lang="mtmacro" line>
   [r:json.fromStrProp("a=1;b=44;c=12")]
   </source>

   Returns
      {"a":1,"c":12,"b":44}
   }}

`Category:JSON Function <Category:JSON_Function>`__
