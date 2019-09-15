.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=indexOf
   |version=1.3b48
   |description=
   Returns the index of a substring in the specified string. If the substring does not occur within the string then -1 is returned. If you do not specify the index to start at the search begins at the start of the string otherwise it will begin from the position you specify.

   |usage=
   <source lang="mtmacro" line>
   indexOf(str, substr)
   </source>
   <source lang="mtmacro" line>
   indexOf(str, substr, start)
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: indexOf("this is a test", "is")]
   </source>
   Returns 2.

   <source lang="mtmacro" line>
   [r: indexOf("this is a test", "is", 3)]
   </source>
   Returns 5.

   <source lang="mtmacro" line>
   [r: indexOf("this is a test", "x")]
   </source>
   Returns -1.
   }}

`Category:String Function <Category:String_Function>`__
