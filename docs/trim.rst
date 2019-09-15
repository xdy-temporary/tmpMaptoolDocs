.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=trim
   |version=1.3b48
   |description=
   Returns a copy of the string that is passed in with the leading and trailing white space removed.

   |usage=
   <source lang="mtmacro" line>
   trim(str)
   </source>
   '''Parameter'''
   {{param|str|The string that has its leading and trailing white space removed.}}

   |examples=
   <source lang="mtmacro" line>
   [r: ":" + trim("     this is a test") + ":"]
   [r: ":" + trim("this is a test      ") + ":"]
   [r: ":" + trim("     this is a test       ") + ":"]
   </source>
   Returns 
       :this is a test:
       :this is a test:
       :this is a test:

   |also=
   {{func|substring}}

   }}

`Category:String Function <Category:String_Function>`__
