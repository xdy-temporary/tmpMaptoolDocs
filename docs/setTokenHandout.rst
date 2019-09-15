.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenHandout
   |version=1.3b77
   |description=
   Sets the handout image for the for the [[Current_Token|Current Token]]. The image can come from several sources. It can be an [[asset_id|asset id]] (like from [[Macros:Functions:tblImage|tblImage()]] or[[Macros:Functions:getTokenImage|getTokenImage()]].)  or a [[Image_Token|Image Token]].

   |usage=
   <source lang="mtmacro" line>
   setTokenHandout(assetId)
   setTokenHandout(assetId, id)
   setTokenHandout(assetId, id, mapname)
   </source>
   <source lang="mtmacro" line>
   setTokenHandout(tokenImageName)
   setTokenHandout(tokenImageName, id)
   setTokenHandout(tokenImageName, id, mapname)
   </source>
   '''Parameters'''
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set the handout, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}
   |changes={{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

`Category:Token Function <Category:Token_Function>`__
