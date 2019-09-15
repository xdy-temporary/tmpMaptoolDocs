.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenPortrait
   |version=1.3b77
   |description=
   Sets the portrait image for the for the [[Current_Token|Current Token]]. The image can come from several sources. It can be an [[asset_id|asset id]] (like from [[Macros:Functions:tblImage|tblImage()]] or[[Macros:Functions:getTokenImage|getTokenImage()]].)  or a [[Image_Token|Image Token]].

   |usage=
   <source lang="mtmacro" line>
   setTokenPortrait(assetId)
   setTokenPortrait(assetId, id)
   setTokenPortrait(assetId, id, mapname)
   </source>
   <source lang="mtmacro" line>
   setTokenPortrait(tokenImageName)
   setTokenPortrait(tokenImageName, id)
   setTokenPortrait(tokenImageName, id, mapname)
   </source>

   '''Parameters'''
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set the portrait, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}
   |changes={{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
