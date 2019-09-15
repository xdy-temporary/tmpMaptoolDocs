.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=resetSize
   |trusted=true
   |version=1.3b48
   |description=
   Resets the [[Size|Size]] of a [[Token|Token]] to the default for grid type of the map it occupies.  See {{func|setSize}} for details about the default size for different grid types.

   |usage=
   <source lang="mtmacro" line>
   resetSize()
   resetSize(id)
   resetSize(id, mapname)
   </source>
   '''Parameters'''
   {{param|id|The token {{code|id}} of the token to reset, defaults to the [[Current_Token|Current Token]].}}
   {{param|mapName|Optional map name to find the token.  Defaults to current map.}}

   |examples=
   To reset the size of the current token to the default for the map:
   <source lang="mtmacro" line>
   [h: resetSize()]
   </source>

   To reset the size of token '''Chocolate Moose''' on map '''Cadbury''':
   <source lang="mtmacro" line>
   [h: tok = "Chocolate Moose"]
   [h: map = "Cadbury"]
   [h: resetSize(tok, map)]
   </source>

   |also=
   {{func|getSize}} {{func|setSize}}

   |changes=
   {{change|1.5.4|Added {{code|mapName}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
