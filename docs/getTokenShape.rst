.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|No examples yet.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenShape
   |proposed=false
   |trusted=false
   |version=1.3b89
   |description=
   Retrieves the token's shape (top-down, circle, square).

   |usage=
   <source lang="mtmacro" line>
   getTokenShape()
   getTokenShape(id)
   getTokenShape(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to check for the shape, defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   '''Result'''<br />
   The function returns the token's shape as a string value: {{code|"TOP-DOWN"}}, {{code|"CIRCLE"}}, {{code|"SQUARE"}}.
   |example=
   This example doesn't really do anything.
   <source lang="mtmacro" line>
   [h: exampleVariable = "a,b,c"]
   [r: exampleFunction(exampleVariable, reverse)]
   </source>
   Returns:
   <source lang="mtmacro" line>
   c,b,a
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|setTokenShape}}
   }}

`Category:Token Function <Category:Token_Function>`__
