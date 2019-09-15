.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDrawingEraser
   |version=1.5.0
   |trusted=true
   |description=
   Returns a value corresponding to the eraser setting of the drawing. A normal visible drawing will return {{code|false}}({{code|0}}), while a drawing that cuts the drawing below it will return {{code|true}}({{code|1}}).
   |usage=
   <source lang="mtmacro" line>
   getDrawingEraser(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getDrawingEraser("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|setDrawingEraser}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
