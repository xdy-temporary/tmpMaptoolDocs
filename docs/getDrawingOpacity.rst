.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDrawingOpacity
   |version=1.5.0
   |trusted=true
   |description=
   Returns a value between 1 and 0 representing the transparency value of a specified drawing.
   |usage=
   <source lang="mtmacro" line>
   getDrawingOpacity(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getDrawingOpacity("Grasslands", "0000000094218C675800000000000000")]
   </source>
   |also=
   {{func|setDrawingOpacity}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
