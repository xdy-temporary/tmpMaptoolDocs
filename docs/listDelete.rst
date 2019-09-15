.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listDelete
   |version=1.3b42
   |description=
   Returns a [[Macros:string_list|string list]] with the specified item deleted from it. The index for the [[Macros:string_list|string list]] 

   |usage=
   <source lang="mtmacro" line>
   listDelete(list, index)
   </source>
   <source lang="mtmacro" line>
   listDelete(list, index, delim)
   </source>

   If delim is not specified then the default value of ',' is used as the value separator in the [[Macros:string_list|string list]]

   |example=
   <source lang="mtmacro" line>
   [r: listDelete("This, is, a, test", 1)] 
   </source>
   Returns This, a, test
   }}

`Category:String List Function <Category:String_List_Function>`__
