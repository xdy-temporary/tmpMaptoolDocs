.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bringDrawingToFront
   |version=1.4.1.7
   |trusted=true
   |description=
   For a specified drawing, moves the drawing to in front of all other drawings on the same layer.
   |usage=
   <source lang="mtmacro" line>
   bringDrawingToFront(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:bringDrawingToFront("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|sendDrawingToBack}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
