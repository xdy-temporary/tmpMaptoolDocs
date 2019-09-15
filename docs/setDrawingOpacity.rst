.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setDrawingOpacity
   |version=1.5.0
   |trusted=true
   |description=
   Sets the transparency value of a specified drawing.
   |usage=
   <source lang="mtmacro" line>
   setDrawingOpacity(mapName, drawingId, opacity)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|opacity|A number between 1 and 0 representing the transparency of the drawing.}}
   |examples=
   <source lang="mtmacro" line>
   [h:setDrawingOpacity("Grasslands", "0000000094218C675800000000000000",0.5)]
   [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]
   </source>
   |also=
   {{func|getDrawingOpacity}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
