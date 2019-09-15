.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenHeight
   |proposed=false
   |trusted=false
   |version=1.3b91
   |description=
   Sets the token's image height in pixels (boundary size).

   |usage=
   <source lang="mtmacro" line>
   setTokenHeight(size, id)
   setTokenHeight(size, id, mapname)
   </source>

   '''Parameters'''
   {{param|size|grid size of the token}}
   {{param|id|The token {{code|id}} of the token to set its height.  Defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   <source lang="mtmacro" line>
   [r: setTokenHeight(300, "Dragon")]
   [r: setTokenHeight(150, "Dragon")]
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|setTokenWidth}}, {{func|getTokenHeight}}, {{func|getTokenWidth}}
   }}

`Category:Token Function <Category:Token_Function>`__
