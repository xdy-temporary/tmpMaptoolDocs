.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=matches
   |version=1.3b48
   |description=
   Returns 1 if a string matches pattern or 0 if it does not. The pattern can be a [[Macros:regular_expression|regular expression]]. Matches performs a while string comparison, so the pattern must match the whole of the input string and not only part of it.

   |usage=
   <source lang="mtmacro" line>
   matches(str, pattern)
   </source>

   |examples=
   <source lang="mtmacro" line>
       [r: matches("This is a test", "test")]
       [r: matches("test", "test")]
       [r: matches("This is a test", ".*test")]

   </source>
   Returns 
       0
       1
       1
   }}

`Category:String Function <Category:String_Function>`__
