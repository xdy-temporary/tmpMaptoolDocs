.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenWidth
   |proposed=false
   |trusted=false
   |version=1.5.1
   |description=
   Retrieves the token's native image width in pixels (native size).

   |usage=
   <source lang="mtmacro" line>
   getTokenNativeWidth()
   getTokenNativeWidth(id)
   getTokenNativeWidth(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to check for its width, defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   '''Result'''<br />
   The token's native (image) width in pixels.
   |example=
   Assuming a token called {{code|"Dragon"}}, with 120px native image width, medium size, on a 50px square grid , then:
   <source lang="mtmacro" line>
   [r: getTokenWidth("Dragon")]
   </source>
   returns:
   <source lang="mtmacro" line>
   120
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|getTokenWidth}}
   {{func|getTokenHeight}}
   {{func|getTokenNativeHeight}}
   }}

`Category:Token Function <Category:Token_Function>`__
