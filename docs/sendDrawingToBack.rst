.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=sendDrawingToBack
   |version=1.4.1.7
   |trusted=true
   |description=
   Moves the specified drawing to be behind of all other drawings on the same layer.

   |usage=
   <source lang="mtmacro" line>
   sendDrawingToBack(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover drawing ids is via the '''Draw Explorer''' interface.}}

   |examples=
   <source lang="mtmacro" line>
   [r:sendDrawingToBack("Grasslands", "0000000074836E675D00000000000000")]
   </source>

   |also=
   {{func|bringDrawingToFront}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
