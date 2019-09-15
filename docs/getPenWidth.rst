.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getPenWidth
   |version=1.5.0
   |trusted=true
   |description=
   Returns the line width for the specified drawing.
   A drawing will have a line width, even if the line itself is not displayed. See setPenColor.
   |usage=
   <source lang="mtmacro" line>
   getPenWidth(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getPenWidth("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|setPenWidth}} {{func|setPenColor}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
