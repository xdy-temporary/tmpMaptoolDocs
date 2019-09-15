.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=refreshDrawing
   |version=1.5.0
   |trusted=true
   |description=
   Causes the specified drawing to be updated on all of the clients connected to the server. If this function is not invoked for each drawing updated by via script, then the client maps will get out of sync.
   |usage=
   <source lang="mtmacro" line>
   refreshDrawing(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover drawing ids is via the '''Draw Explorer''' interface.}}
   |example=
   <source lang="mtmacro" line>
   [h:setFillColor("Grasslands", "00000000CCF6B567CC00000000000000","blue")]
   [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]
   </source>
   |also=
   {{func|setFillColor}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
