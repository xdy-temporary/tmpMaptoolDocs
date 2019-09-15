.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listAppend
   |version=1.3b42
   |description=
   Returns a [[Macros:string_list|string list]] with a value appended to the end of the [[Macros:string_list|string list]].

   |usage=
   <source lang="mtmacro" line>
   listAppend(list, value)
   </source>
   <source lang="mtmacro" line>
   listAppend(list, value, delim)
   </source>

   If delim is not specified then the default value of ',' is used to separate the values in the [[Macros:string_list|string list]]

   |examples=
   <source lang="mtmacro" line>
   [r: listAppend("This, is, a", "test")]
   </source>
   Returns This, is, a, test

   <source lang="mtmacro" line>
   [r: listAppend("This: is: a:", "test", ":")] 
   </source>
   Returns This: is: a: test
   }}

`Category:String List Function <Category:String_List_Function>`__
