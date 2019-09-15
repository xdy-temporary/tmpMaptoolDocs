.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=lastIndexOf
   |version=1.3b48
   |description=
   Finds the index in a string of the last occurrence of a substring in a string. If the substring does not occur in the string then -1 is returned. The index for the string starts at 0.

   |usage=
   <source lang="mtmacro" line>
   lastIndexOf(str, substr)
   </source>

   |example=
   <source lang="mtmacro" line>
   [lastIndexOf("abcde", "c")]
   </source>
   Returns 2

   <source lang="mtmacro" line>
   [lastIndexOf("abcde", "z")]
   </source>
   Returns -1
   }}

`Category:String Function <Category:String_Function>`__
