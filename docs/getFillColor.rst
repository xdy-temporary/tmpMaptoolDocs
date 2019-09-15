.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getFillColor
   |version=1.5.0
   |trusted=true
   |description=
   Returns a string representing the colour or texture of the pen for a specified drawing.
   A colour will be returned in the hex format (i.e. "#000000" for black) while a texture will be returned as the asset url (i.e. "asset://ffff0fe019c241c7456b0ec0b347ef37")
   |usage=
   <source lang="mtmacro" line>
   getFillColor(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getFillColor("Grasslands", "0000000074836E675D00000000000000")]
   </source>
   |also=
   {{func|setFillColor}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
