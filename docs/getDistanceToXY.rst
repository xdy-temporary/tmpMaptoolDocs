.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDistanceToXY
   |version=1.3b51
   |description=
   Gets the distance to a target grid cell.

   |usage=
   <source lang="mtmacro" line>
   getDistanceToXY(x, y)
   </source>
   <source lang="mtmacro" line>
   getDistanceToXY(x, y, units)
   </source>
   <source lang="mtmacro" line>
   getDistanceToXY(x, y, units, source)
   </source>
   <source lang="mtmacro" line>
   getDistanceToXY(x, y, units, source, metric)
   </source>
   '''Parameters'''
   * {{code|x}} - The X coordinate of the target grid cell.
   * {{code|y}} - The Y coordinate of the target grid cell.
   * {{code|units}} - If set to {{code|false}}({{code|0}}) the distance is returned in cells. Default is returning Distance Per Cell units.
   * {{code|source}} - The id of the token to measure the distance from. Default is the current token.
   * {{param|metric|The movement metric to use which defaults to the movement metric in the users preferences, the metric can be one of the following strings}}
   ** {{code|NO_GRID}} - The grid is ignored and straight line distance between the tokens is returned.
   ** {{code|ONE_TWO_ONE}} - First Diagonal movement costs 1, second 2, and so on (Square grid only).
   ** {{code|ONE_ONE_ONE}} - Diagonal movement costs a single square (Square grid only).
   ** {{code|MANHATTAN}} - Diagonal movement costs 2 (Square grid only).
   ** {{code|NO_DIAGONALS}} - No diagonal movement is allowed (Square grid only).

   |example=
   To get the distance from the current token to 10,10.
   <source lang="mtmacro" line>
   [h: dist = getDistanceToXY(10, 10)]
   </source>

   To get the distance between the ''Altar'' and 10, 10 in the number of squares or hexes.
   <source lang="mtmacro" line>
   [h: dist = getDistanceToXY(10, 10, 0, "Altar")]
   </source>

   To get the distance between the ''Altar'' and 10, 10 in ''map distance'' units.
   <source lang="mtmacro" line>
   [h: dist = getDistanceToXY(10, 10, 1, "Altar")]
   </source>

   To get the straight line distance between the ''Altar'' and 10, 10.
   <source lang="mtmacro" line>
   [h: dist = getDistanceToXY(10, 10, 1, "Altar", "NO_GRID")]
   </source>

   |also=
   {{func|getDistance}} {{func|getTokens}}

   |changes=
   {{change|1.3b55|Added the optional {{code|metric}} argument.}}
   }}

`Category:Distance Function <Category:Distance_Function>`__
