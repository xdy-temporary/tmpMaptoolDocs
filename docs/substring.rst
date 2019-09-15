.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=substring
   |version=1.3b48
   |description=
   Returns the substring of the string from the start to the end indexes. Indexes for strings start at 0. If the end parameter is not specified then the substring extends to the end of the string.

   |usage=
   <source lang="mtmacro" line>
   substring(str, start)
   </source>
   <source lang="mtmacro" line>
   substring(str, start, end)
   </source>

   |examples=
   <source lang="mtmacro" line>
       [substring("This is a test", 5)]
       [substring("This is a test", 5, 7)]
   </source>
   Returns 
       is a test
       is
   }}

`Category:String Function <Category:String_Function>`__
