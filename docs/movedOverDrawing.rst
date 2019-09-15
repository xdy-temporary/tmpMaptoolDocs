.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=movedOverDrawing
   |version=1.5.2
   |trusted=true
   |description=
   Use to check if a given path has crossed through a specified drawing.

   Returns a JSON array with coordinates of all cells in the path that overlap with the area defined by the given drawing.
   |usage=
   <source lang="mtmacro" line>
   getDrawingInfo(mapName, drawingId, path)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|path|JSON array of X/Y coordinate such as that returned by {{func|getLastPath}}}}
   |examples=
   <source lang="mtmacro" line>
   [h: lp = getLastPath()]
   [h: id = findDrawings(getCurrentMapName(),"fig1")] 
   [r: movedOverDrawing(getCurrentMapName(),id,lp)]
   </source>

   |also=
   {{func|getDrawingInfo}} {{func|getLastPath}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
