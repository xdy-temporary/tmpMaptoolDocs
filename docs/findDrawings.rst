.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=findDrawings
   |version=1.5.0
   |trusted=true
   |description=
   Returns the id or ids of any drawing on the specified map that match the name parameter.
   |usage=
   <source lang="mtmacro" line>
   findDrawings(mapName, name)
   findDrawings(mapName, name, delim)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|name|A string containing name of the searched for drawings. The only way to name a drawing is via the Draw Explorer interface.}}
   {{param|delim|Optional separator. If not specified the default value {{code|","}} is used.  If {{code|"json"}} is specified, a JSON array is returned instead of a String List.}}
   |example=
   <source lang="mtmacro" line>
   [h:id=findDrawings("Grasslands", "block")]
   [h:setFillColor("Grasslands", id,"#000000")]
   [h:refreshDrawing("Grasslands", id)]
   </source>
   |also=
   {{func|setFillColor}} {{func|refreshDrawing}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
