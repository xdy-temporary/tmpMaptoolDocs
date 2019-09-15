.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDrawingLayer
   |version=1.5.0
   |trusted=true
   |description=
   For a specified drawing, returns the layer to which the drawing belongs.
   |usage=
   <source lang="mtmacro" line>
   getDrawingLayer(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getDrawingLayer("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|setDrawingLayer}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
