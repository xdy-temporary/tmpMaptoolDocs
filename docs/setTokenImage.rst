.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenImage
   |version=1.3b48
   |description=
   Sets the image for the for the [[Current_Token|Current Token]]. The image can come from several sources. It can come from a function that returns an [[asset_id|asset id]] such as [[Macros:Functions:tblImage|tblImage()]] or [[Macros:Functions:getTokenImage|getTokenImage()]]. Or it could come from a [[Image_Token|Image Token]].

   |usage=
   <source lang="mtmacro" line>
   setTokenImage(assetId)
   setTokenImage(assetId, id)
   setTokenImage(assetId, id, mapname)
   </source>
   <source lang="mtmacro" line>
   setTokenImage(tokenImageName)
   setTokenImage(tokenImageName, id)
   setTokenImage(tokenImageName, id, mapname)
   </source>
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set the image, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [h: setTokenImage(tblImage("elfImages", 1))]
   [h: setTokenImage("image:Elf-Dead")]
   </source>
   |changes={{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

`Category:Token Function <Category:Token_Function>`__
