.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listGet
   |version=1.3b42
   |description=
   Returns the value in the [[Macros:string_list|string list]] at the specified index. The index for a [[Macros:string_list|string list]] starts at 0.

   |usage=
   <source lang="mtmacro" line>
   listGet(list, index)
   </source>
   <source lang="mtmacro" line>
   listGet(list, index, delim)
   </source>

   If delim is not specified then the default value of ',' is used as the value separator in the [[Macros:string_list|string list]]

   |example=
   <source lang="mtmacro" line>
   [r: listGet("This, is, a , test", 2)]
   </source>
   Returns a

   <source lang="mtmacro" line>
   [r: listGet("This: is: a :test", 1, ":")] 
   </source>
   Returns is
   }}

`Category:String List Function <Category:String_List_Function>`__
