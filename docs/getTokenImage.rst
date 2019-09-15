.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenImage
   |description=
   Returns the [[Asset_ID|asset id]] of the image for the for the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   getTokenImage()
   getTokenImage(size)
   getTokenImage(size, id)
   getTokenImage(size, id, mapname)
   </source>

   '''Parameters'''
   {{param|size|OPTIONAL: The size the picture should be returned as. If a blank string "", no size adjustment is done. Defaults to "".}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to retrieve the token image, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   To display the image for the current [[Token:token|token]].
   <source lang="mtmacro" line>
   <img src='[r:getTokenImage()]'></img>
   </source>

   To get the image of any [[Token:token|token]] using its id and the token roll option.
   <source lang="mtmacro" line>
   [h, token(tokenId): imgAsset = getTokenImage()] 
   </source>
   |changes={{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   |also=
   [[getImage|getImage]]
   }}

`Category:Token Function <Category:Token_Function>`__
