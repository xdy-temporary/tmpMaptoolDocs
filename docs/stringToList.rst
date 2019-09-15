.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=stringToList
   |version=1.3b48
   |description=
   Converts a string into a [[Macros:string_list|string list]] using a pattern to determine separator between elements. The specified delimiter is used to separate the elements in the [[Macros:string_list|Macros:string list]] if it is specified, otherwise the default value of "," is used.  Pattern can be a [[Macros:regular_expression|regular expression]].

   |usage=
   <source lang="mtmacro" line>
   stringToList(str, pattern)
   </source>
   <source lang="mtmacro" line>
   stringToList(str, pattern, delim)
   </source>

   |examples=
   <source lang="mtmacro" line>
       [stringToList("This is a test", " ")]
       [stringToList("1,2,3,4", ",", ":")]
   </source>
   Returns 
       This,is,a,test
       1:2:3:4
   }}

`Category:String List Function <Category:String_List_Function>`__
