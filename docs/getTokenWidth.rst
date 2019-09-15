.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenWidth
   |proposed=false
   |trusted=false
   |version=1.3b89
   |description=
   Retrieves the token's image width in pixels (boundary size).

   |usage=
   <source lang="mtmacro" line>
   getTokenWidth()
   getTokenWidth(id)
   getTokenWidth(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to check for its width, defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   '''Result'''<br />
   The token's boundary (image) width in pixels.
   |example=
   Assuming a token called {{code|"Dragon"}}, medium size, on a 50px square grid, then:
   <source lang="mtmacro" line>
   [r: getTokenWidth("Dragon")]
   </source>
   returns:
   <source lang="mtmacro" line>
   50
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|getTokenHeight}}
   {{func|getTokenNativeHeight}}
   {{func|getTokenNativeWidth}}
   }}

`Category:Token Function <Category:Token_Function>`__
