.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenSnapToGrid
   |version=1.4
   |description=
   Sets the "snap to" behaviour for the [[Current_Token|Current Token]] or a specified token.

   |usage=
   <source lang="mtmacro" line>
   setTokenSnapToGrid(snap)
   setTokenSnapToGrid(snap, id)
   setTokenSnapToGrid(snap, id, mapname)
   </source>

   '''Parameters'''
   {{param|snap|A value {{true}} or {{false}}.}}
   {{param|id|The id of the token to set its snap behaviour.}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   <source lang="mtmacro" line>
   [h: setTokenSnapToGrid(0)]
   [h: setTokenSnapToGrid(1, currentToken())]</source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   |also=
   {{func|isSnapToGrid}}
   }}

`Category:Token Function <Category:Token_Function>`__
