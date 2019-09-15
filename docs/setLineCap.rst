.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setLineCap
   |version=1.5.0
   |trusted=true
   |description=
   Sets the line cap setting of the drawing that corresponds to the map and drawing id. If Set to {{code|round}}({{code|0}}) the drawing will display with round line ends, but if set to {{code|square}}({{code|1}}) the drawing display with square line ends and angled corners.
   |usage=
   <source lang="mtmacro" line>
   getLineCap(mapName, drawingId, capType)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|capType|The value of the setting to set, {{code|round}}({{code|0}}) or {{code|square}}({{code|1}}).}}
   |example=
   <source lang="mtmacro" line>
   [h:setLineCap("Grasslands", "0000000094218C675800000000000000",0)]
   [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]
   [h:setLineCap("Grasslands", "00000000CCF6B567CC00000000000000",1)]
   [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]
   </source>
   |also=
   {{func|getLineCap}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
