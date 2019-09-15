.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setSize
   |trusted=true
   |version=1.3b48
   |description=
   Sets the size of a [[Token|Token]] with one of the defined sizes according to each Grid Type.  The sizes can be found on the [[Token_Size|Token Size]] page.

   |usage=
   <source lang="mtmacro" line>
   setSize(size)
   setSize(size, id)
   setSize(size, id, mapname)
   </source>
   '''Parameters'''
   {{param|size|The [[size|Token Size]] to set the token to.}}
   {{param|id|The token {{code|id}} of the token which will have its [[size|Token Size]] set. Defaults to the [[Current_Token|Current Token]].}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   To set the size of the current token to {{code|Medium}}:
   <source lang="mtmacro" line>
   [h: setSize("Medium")]
   </source>

   To set the size of the current token to whatever string is stored in the macro variable '''mySize''':
   <source lang="mtmacro" line>
   [h: mySize = "Large"]
   [h: setSize(mySize)]
   </source>

   |also=
   {{func|getSize}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
