.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=startsWith
   |version=1.3b49
   |description=
   Returns {{true}} if the first parameter starts with the contents of the second parameter.

   |usage=
   <source lang="mtmacro" line>
   [h: result = startsWith(string, substring)]
   </source>

   Returns {{true}} if the string starts with a certain substring and {{false}} if not.

   |examples=
   <source lang="mtmacro" line>
   [r: startsWith("Test", "T")]
   [r: startsWith("Test", "Te")]
   [r: startsWith("Test", "Tez")]
   </source>

   '''Returns'''
   <pre>  1
     1
     0</pre>
   }}

`Category:String Function <Category:String_Function>`__
