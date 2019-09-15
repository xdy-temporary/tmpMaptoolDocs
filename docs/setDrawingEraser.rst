.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setDrawingEraser
   |version=1.5.0
   |trusted=true
   |description=
   Sets the eraser setting of the drawing that corresponds to the map and drawing id. If Set to {{code|false}}({{code|0}}) the drawing will be displayed normally, but if set to {{code|true}}({{code|1}}) the drawing will erase all below.
   |usage=
   <source lang="mtmacro" line>
   setDrawingEraser(mapName, drawingId, boolean)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|boolean|The value of the setting to set, {{code|true}}({{code|1}}) or {{code|false}}({{code|0}}).}}
   |example=
   <source lang="mtmacro" line>
   [h:setDrawingEraser("Grasslands", "0000000094218C675800000000000000",0)]
   [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]
   [h:setDrawingEraser("Grasslands", "00000000CCF6B567CC00000000000000",1)]
   [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]
   </source>
   |also=
   {{func|getDrawingEraser}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
