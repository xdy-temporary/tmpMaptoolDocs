.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=lower
   |version
   |description=
   Returns the lower case version of a string. If the number of characters is not specified then the whole string is converted to lower case.

   |usage=
   <source lang="mtmacro" line>
   lower(str)
   </source>
   <source lang="mtmacro" line>
   lower(str, numChars)
   </source>

   |example=
   <source lang="mtmacro" line>
   [r: lower("This Is a Test")]
   [r: lower("This Is a Test", 1)]
   </source>
   Returns 
      this is a test
      this Is a Test
   }}

`Category:String Function <Category:String_Function>`__
