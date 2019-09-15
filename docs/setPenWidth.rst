.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setPenWidth
   |version=1.5.0
   |trusted=true
   |description=
   Sets the line width for a specified drawing.
   Regardless of the set width, a line will only be visible if it has a visible colour. See setPenColor.
   |usage=
   <source lang="mtmacro" line>
   setPenWidth(mapName, drawingId, width)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   {{param|width|A number for the desired line thickness.}}
   |examples=
   <source lang="mtmacro" line>
   [h:setPenWidth("Grasslands", "0000000094218C675800000000000000",10)]
   [h:setPenWidth("Grasslands", "0000000087318B505800000000000000",3)]
   </source>
   |also=
   {{func|getPenWidth}} {{func|setPenColor}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
