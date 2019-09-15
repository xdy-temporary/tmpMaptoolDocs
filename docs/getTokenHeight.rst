.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenHeight
   |proposed=false
   |trusted=false
   |version=1.3b89
   |description=
   Retrieves the token's image height in pixels (boundary size).

   |usage=
   <source lang="mtmacro" line>
   getTokenHeight()
   getTokenHeight(id)
   getTokenHeight(id, mapname)
   </source>

   '''Parameter'''
   {{param|id|The token id of the token to check for its height, defaults to the [[Current_Token|Current Token]].}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   '''Result'''<br />
   The token's boundary (image) height in pixels.
   |example=
   Assuming a token called {{code|"Dragon"}}, medium size, on a 50px square grid, then:
   <source lang="mtmacro" line>
   [r: getTokenHeight("Dragon")]
   </source>
   returns:
   <source lang="mtmacro" line>
   50
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|getTokenNativeHeight}}
   {{func|getTokenWidth}}
   {{func|getTokenNativeWidth}}
   }}

`Category:Token Function <Category:Token_Function>`__
