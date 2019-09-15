.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|lastPath-format specified, define/explain return value, examples}}

.. raw:: mediawiki

   {{MacroFunction
   |name=movedOverPoints
   |version=1.3.b75
   |description=
   Use to check if a token has moved through a shape that is defined by an array of pixel coordinates (formatted like the one received from {{func|getLastPath}} or the {{code|onTokenMove}} event.

   Returns a JSON array with coordinates of all cells in the token's path that overlap with the area defined by the given points.

   Where each coordinate pair returned is dependent on the grid type:
   * Square:  Coordinates are the top-left corner.
   * Hex:  Coordinates are the center point of the cell.
   * Isometric:  Coordinates are the right-most point of the cell.
   * Gridless: Returns just the top-left corner of the token's ending location.

   |usage=
   <source lang="mtmacro" line>
   movedOverPoints(points)
   movedOverPoints(points,path)
   </source>

   '''Parameters'''
   {{param|points|JSON array of X/Y coordinate X/Y pairs that defines a polygon}}
   {{param|path|JSON array of X/Y coordinate such as that returned by {{func|getLastPath}}}}

   |example=
   <source lang="mtmacro" line>
   <!-- lets define a shape -->

   [h: jsonArray = json.append("",
       json.set("", "x",   0, "y",   0),
       json.set("", "x",   0, "y", 100),
       json.set("", "x", 100, "y", 100),
       json.set("", "x",   100, "y", 0)
   )]

   <!-- check if token in context has moved through that shape -->
   [r: movedOverPoints(jsonArray)]
   </source>

   '''With Second Parameter'''

   <source lang="mtmacro" line>
   [h: jsonArray = json.append("",
       json.set("", "x", 250, "y", 250),
       json.set("", "x", 250, "y", 550),
       json.set("", "x", 550, "y", 550),
       json.set("", "x", 550, "y", 250)
   )]

   Last Path: [r: lastPath = getLastPath()]
   <br>
   Moved Over: [r: movedOverPoints(jsonArray,lastPath)]
   </source>

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
