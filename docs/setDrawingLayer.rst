.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setDrawingLayer
   |version=1.4.1.7
   |trusted=true
   |description=
   For a specified drawing, set the layer of the map to which the drawing belongs.

   The [[Map_Layer|Map Layer]] is one of:
   * {{code|TOKEN}}
   * {{code|GM}} also known as Hidden
   * {{code|OBJECT}}
   * {{code|BACKGROUND}}
    

   |usage=
   <source lang="mtmacro" line>
   setDrawingLayer(mapName, drawingId, layer)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|layer|The layer to move the drawing to.}}
   |example=
   <source lang="mtmacro" line>
   [h:setDrawingLayer("Grasslands", "0000000074836E675D00000000000000","GM")]
   [h:refreshDrawing("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|getDrawingLayer}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
