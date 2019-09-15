.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=endsWith
   |version=1.3b49
   |description=Returns 1 if the string ends with a certain sub string.

   |usage=
   <source lang="mtmacro" line>
   [h: result = endsWith(str, substr)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: endsWith("Test", "t")]
   [r: endsWith("Test", "st")]
   [r: endsWith("Test", "z")]
   </source>

   Returns
       1
       1
       0
   }}

`Category:String Function <Category:String_Function>`__
