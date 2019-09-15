.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listContains
   |version=1.3b42
   |description=
   Returns the number of occurrences of a value in a [[String_List|String List]].

   |usage=
   <source lang="mtmacro" line>
   listContains(list, value)
   listContains(list, value, delim)
   </source>
   '''Parameters'''
   {{param|list|The [[String_List|String List]] that is checked for occurrences of the {{code|value}}.}}
   {{param|value|The value to search the [[String_List|String List]] for occurrences.}}
   {{param|delim|The delimiter that separates the values in the [[String_List|String List]]; defaults to {{code|","}}.}}

   |examples=
   <source lang="mtmacro" line>
   [r: listContains("a,b,c,a,b,a", "a")]
   </source>
   Returns {{code|3}}

   <source lang="mtmacro" line>
   [h: MyStringList = "1#2#3#4#1#2#3#1#2"]
   [r: listContains(MyStringList, "3", "#")]
   </source>
   Returns {{code|2}}

   |also=
   {{func|listFind}}

   }}

`Category:String List Function <Category:String_List_Function>`__
