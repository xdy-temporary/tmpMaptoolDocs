.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getLineCap
   |version=1.5.0
   |trusted=true
   |description=
   Returns a value corresponding to the line type setting of the drawing. A line with round ends will return {{code|round}}({{code|0}}), while a line with square ends will return {{code|square}}({{code|1}}). This function will return a value regardless of whether or not the drawing line is visible.
   |usage=
   <source lang="mtmacro" line>
   getDrawingEraser(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getLineCap("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|setLineCap}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
