.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setPenColor
   |version=1.5.0
   |trusted=true
   |description=
   Sets the colour or texture of the pen for a specified drawing.
   |usage=
   <source lang="mtmacro" line>
   setPenColor(mapName, drawingId, paint)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|paint|A string representing the colour or texture of the pen.}}
   |examples=
   <source lang="mtmacro" line>
   [r:setPenColor("Grasslands", "0000000094218C675800000000000000","red")]
   [r:setPenColor("Grasslands", "0000000094218C675800000000000000","#ff0000")]
   [r:setPenColor("Grasslands", "0000000094218C675800000000000000","asset://ffff0fe019c241c7456b0ec0b347ef37")]
   </source>
   |also=
   {{func|getPenColor}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
