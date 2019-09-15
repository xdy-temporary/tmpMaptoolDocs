.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=decode
   |version=1.3b48
   |description=Decodes a string that was encoded with the [[encode|encode()]] function. The [[encode|encode()]] and decode() functions can be used to encode a property list so that it can be embedded within another property list.

   |usage=
   <source lang="mtmacro" line>
   decode(str)
   </source>

   |example=
   <source lang="mtmacro" line>
   [h: getStrProp(decode(getStrProp(inv, "Weapons"), "Name")]
   </source>
   }}

`Category:String Function <Category:String_Function>`__
