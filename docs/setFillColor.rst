.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setFillColor
   |version=1.5.0
   |trusted=true
   |description=
   Sets the colour or texture of the pen for a specified drawing.
   |usage=
   <source lang="mtmacro" line>
   setFillColor(mapName, drawingId, paint)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|paint|A string representing the fill colour or fill texture.}}
   |example=
   <source lang="mtmacro" line>
   [h:setFillColor("Grasslands", "0000000094218C675800000000000000","red")]
   [h:setFillColor("Grasslands", "0000000094218C675800000000000000","#ff0000")]
   [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]
   [h:setFillColor("Grasslands", "00000000CCF6B567CC00000000000000","asset://ffff0fe019c241c7456b0ec0b347ef37")]
   [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]
   </source>
   |also=
   {{func|getFillColor}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
