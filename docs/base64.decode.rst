.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=base64.decode
   |trusted=false
   |version=1.5.2
   |description=
   Accepts a [https://en.wikipedia.org/wiki/Base64 Base64] encoded string and decodes it to plain text.

   |usage=
   <source lang="mtmacro" line>
   base64.decode(string)
   </source>
   '''Parameters'''
   {{param|string|The base64 encoded string to be decoded.}}

   |example=
   Encode a string and then decode it.

   <source lang="mtmacro" line>
   [r: txt = "Four score and seven years ago..."]<br>
   [r: encTxt = base64.encode(txt)]<br>
   [r: base64.decode(encTxt)]<br></source>
   '''Returns:'''
   <source lang="mtmacro" line>
   Four score and seven years ago... 
   Rm91ciBzY29yZSBhbmQgc2V2ZW4geWVhcnMgYWdvLi4u 
   Four score and seven years ago...
   </source>

   |also=
   {{func|base64.encode}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
