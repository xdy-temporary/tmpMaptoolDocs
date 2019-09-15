.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDistance
   |trusted=true
   |version=1.3b51
   |description=
   Returns the distance between two tokens or objects. 

   |usage=
   <source lang="mtmacro" line>
   getDistance(target)
   </source>
   <source lang="mtmacro" line>
   getDistance(target, units)
   </source>
   <source lang="mtmacro" line>
   getDistance(target, units, source)
   </source>
   <source lang="mtmacro" line>
   getDistance(target, units, source, metric)
   </source>
   '''Parameters'''
   {{param|target|The id of the token that the distance is measured to.}}
   {{param|units|If set to {{code|false}}({{code|0}}), the distance is given in cells, otherwise the default is to return the distance in Distance Per Cell units.}}
   {{param|source|The id of the token to measure the distance from, the default is the current token.}}
   {{param|metric|The movement metric to use which defaults to the movement metric in the users preferences, the metric can be one of the following strings}}
   ** {{code|NO_GRID}} - The grid is ignored and straight line distance between the tokens is returned.
   ** {{code|ONE_TWO_ONE}} - First Diagonal movement costs 1, second 2, and so on (Square grid only).
   ** {{code|ONE_ONE_ONE}} - Diagonal movement costs a single square (Square grid only).
   ** {{code|MANHATTAN}} - Diagonal movement costs 2 (Square grid only).
   ** {{code|NO_DIAGONALS}} - No diagonal movement is allowed (Square grid only).

   |example=
   To get the distance from the current token to the ''Altar''.
   <source lang="mtmacro" line>
   [h: dist = getDistance("Altar")]
   </source>

   To get the distance between the ''Altar'' and the ''Sacrifice'' in the number of squares or hexes.
   <source lang="mtmacro" line>
   [h: dist = getDistance("Altar", 0, "Sacrifice")]
   </source>

   To get the distance between the ''Altar'' and the ''Sacrifice'' in ''map distance'' units.
   <source lang="mtmacro" line>
   [h: dist = getDistance("Altar", 1, "Sacrifice")]
   </source>

   To get the straight line distance between the ''Altar'' and the ''Sacrifice''.
   <source lang="mtmacro" line>
   [h: dist = getDistance("Altar", 1, "Sacrifice", "NO_GRID")]
   </source>

   |also= {{func|getDistanceToXY}} {{func|getTokens}}
   |changes=
   {{change|1.3b55|Added the optional {{code|metric}} argument.}}
   }}

`Category:Distance Function <Category:Distance_Function>`__
