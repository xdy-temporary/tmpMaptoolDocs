.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listFind
   |version=1.3b42
   |description=
   Returns the index of the first occurrence of a value in a [[Macros:string_list|string list]]. If the value is not found then -1 is returned.

   |usage=
   <source lang="mtmacro" line>
   listFind(list, value)
   </source>
   <source lang="mtmacro" line>
   listFind(list, value, delim)
   </source>

   If delim is not specified then the default value of ',' is used as the value separator in the [[Macros:string_list|string list]]

   |examples=
   <source lang="mtmacro" line>
   [r: listFind("This, is, a, test", "is")]
   </source>
   Returns 1

   <source lang="mtmacro" line>
   [r: listFind("This: is: a: test", "a", ":")]
   </source>
   Returns 2

   <source lang="mtmacro" line>
   [r: listFind("This, is, a, test", "not")]
   </source>
   Returns -1
   }}

`Category:String List Function <Category:String_List_Function>`__
