.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getFindCount
   |version=1.3b48
   |description=Returns the number of times that [[strfind|strfind()]] was able to match the input string.

   |usage=
   <source lang="mtmacro" line>
   getFindCount(id)
   </source>

   The id is the id value returned by [[Macros:Functions:strfind|strfind()]].

   |example=
   <source lang="mtmacro" line>
   [h: id = strfind("this is a test", "(\\S+)\\s+(\\S+)\\s*")]
   [r: getFindCount(id)]
   </source>
   Returns 2.
   }}

`Category:String Function <Category:String_Function>`__
