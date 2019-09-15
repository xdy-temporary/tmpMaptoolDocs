.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|No examples yet.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenShape
   |proposed=false
   |trusted=false
   |version=1.3b89
   |description=
   Sets the token's shape (top down, circle, square, figure).

   |usage=
   <source lang="mtmacro" line>
   setTokenShape(shape)
   setTokenShape(shape, id)
   setTokenShape(shape, id, mapname)
   </source>
   '''Parameters'''
   {{param|shape|String value: {{code|"TOP DOWN"}}, {{code|"CIRCLE"}}, {{code|"SQUARE"}}, {{code|"FIGURE"}}.}}
   {{param|id|The token id of the token to set to a new shape, defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   '''Result'''<br />
   The function returns the token's shape as a string value: {{code|"TOP DOWN"}}, {{code|"CIRCLE"}}, {{code|"SQUARE"}}, {{code|"FIGURE"}}.

   |example=
   On current token.
   <source lang="mtmacro" line>
   [h: newShape = "CIRCLE"]
   [r: setTokenShape(newShape)]
   </source>
   Returns:
   <source lang="mtmacro" line>
   Circle
   </source>
   With Token ID.
   <source lang="mtmacro" line>
   [h: newShape = "TOP DOWN"]
   [h: tokenName = "Some Token"]
   [r: setTokenShape(newShape,tokenName)]
   </source>
   Returns:
   <source lang="mtmacro" line>
   Top down
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|getTokenShape}}
   }}

`Category:Token Function <Category:Token_Function>`__
