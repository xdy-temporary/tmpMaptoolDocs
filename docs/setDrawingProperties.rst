.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setDrawingProperties
   |version=1.5.0
   |trusted=true
   |description=
   Sets the properties for a specified drawing. Currently this can only be used in conjunction with the getDrawingProperties function.
   |usage=
   <source lang="mtmacro" line>
   setDrawingProperties(mapName, drawingId, properties)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|properties|The properties of another drawing. Currently this can only be delivered via the getDrawingProperties function}}
   |examples=
   <source lang="mtmacro" line>
   [h:fromId="0000000074836E675D00000000000000"]
   [h:toId="0000000095C36B437D00000000000000"]
   [h:setDrawingProperties("Grasslands", toId, getDrawingProperties("Grasslands", fromId))]
   </source>
   |also=
   {{func|getDrawingProperties}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
