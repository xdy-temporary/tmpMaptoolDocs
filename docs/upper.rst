.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=upper
   |version=1.3b48
   |description=
   Returns the upper case version of a string. If the number of characters is not specified then the whole string is converted to upper case.

   |usage=
   <source lang="mtmacro" line>
   upper(str)
   </source>
   <source lang="mtmacro" line>
   upper(str, numChars)
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: upper("this Is a Test")]
   [r: upper("this Is a Test", 1)]
   </source>
   Returns 
      THIS IS A TEST
      This Is a Test
   }}

`Category:String Function <Category:String_Function>`__
