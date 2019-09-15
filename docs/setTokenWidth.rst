.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenWidth
   |proposed=false
   |trusted=false
   |version=1.3b91
   |description=
   Sets the token's image width in pixels (boundary size).

   |usage=
   <source lang="mtmacro" line>
   setTokenWidth(size)
   setTokenWidth(size, id)
   setTokenWidth(size, id, mapname)
   </source>

   '''Parameters'''
   {{param|size|grid size of the token}}
   {{param|id|The token {{code|id}} of the token to set its width.  Defaults to the [[Current_token|Current token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [r: setTokenWidth(300, "Dragon")]
   [r: setTokenHeight(150, "Dragon")]
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|setTokenHeight}}, {{func|getTokenHeight}}, {{func|getTokenWidth}}
   }}

`Category:Token Function <Category:Token_Function>`__
