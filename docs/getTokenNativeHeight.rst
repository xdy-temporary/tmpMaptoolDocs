.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenNativeHeight
   |proposed=false
   |trusted=false
   |version=1.5.1
   |description=
   Retrieves the token's native image height in pixels (native size).

   |usage=
   <source lang="mtmacro" line>
   getTokenNativeHeight()
   getTokenNativeHeight(id)
   getTokenNativeHeight(id, mapname)
   </source>

   '''Parameter'''
   {{param|id|The token id of the token to check for its height, defaults to the [[Current_Token|Current Token]].}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   '''Result'''<br />
   The token's native(image) height in pixels.
   |example=
   Assuming a token called {{code|"Dragon"}}, with 120px native image height, medium size, on a 50px square grid , then:
   <source lang="mtmacro" line>
   [r: getTokenNativeHeight("Dragon")]
   </source>
   returns:
   <source lang="mtmacro" line>
   120
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|getTokenHeight}}
   {{func|getTokenWidth}}
   {{func|getTokenNativeWidth}}
   }}

`Category:Token Function <Category:Token_Function>`__
