.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listCount
   |version=1.3b42
   |description=
   Returns the number of items in a [[Macros:string_list|string list]].

   |usage=
   <source lang="mtmacro" line>
   listCount(list)
   </source>
   <source lang="mtmacro" line>
   listCount(list, delim)
   </source>

   If delim is not specified then the default value of ',' is used as the value separator in the [[Macros:string_list|string list]]

   |examples=
   <source lang="mtmacro" line>
   [r: listCount("This, is, a, test")]
   </source>
   Returns 4

   <source lang="mtmacro" line>
   [r: listCount("This: is: a: test",":")] 
   </source>
   Returns 4
   }}

`Category:String List Function <Category:String_List_Function>`__
