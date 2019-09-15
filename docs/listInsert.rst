.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listInsert
   |version=1.3b42
   |description=
   Inserts a value into the [[Macros:string_list|string list]] at the specified index. If a delimiter is not specified then the default value of ',' is used. The index for lists starts at 0

   |usage=
   <source lang="mtmacro" line>
   listInsert(list, index, value)
   </source>
   <source lang="mtmacro" line>
   listInsert(list, index, value, delim)
   </source>

   |example=
   <source lang="mtmacro" line>
   [r: listInsert("This, a , test", 1, "is")]
   </source>
   Returns This, is, a, Test

   <source lang="mtmacro" line>
   [r: listInsert("This: a: test", 1, "is", ":")] 
   </source>
   Returns This: is: a: test
   }}

`Category:String List Function <Category:String_List_Function>`__
