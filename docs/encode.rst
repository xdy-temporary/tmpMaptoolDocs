.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=encode
   |version=1.3b48
   |description=Encodes a string that was can be decoded with the [[decode|decode()]] function. The [[decode|decode()]] and encode() functions can be used to encode a property list so that it can be embedded within another property list.

   |usage=
   <source lang="mtmacro" line>
   encode(str)
   </source>

   |example=
   <source lang="mtmacro" line>
   [h: innerPropList = encode("val1=blah ; val2=blahblah")]
   [h: props = setStrProp(props, key, innerPropList)]
   </source>
   }}

`Category:String Function <Category:String_Function>`__
