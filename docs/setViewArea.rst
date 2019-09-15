.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setViewArea
   |version=1.5
   |description=
   Sets the currently viewed screen area, set by two sets of cell coordinates, so that the two cells are at the edge of the screen. If the map is "gridless", the coordinates will be pixel coordinates. A final optional parameter causes the view of any connected players to be set the same. Only GMs or trusted macros can trigger the view of all players to change.

   |usage=
   <source lang="mtmacro" line>
   setViewArea(startX, startY, endX, endY [, pixels [, allPlayers]])
   </source>

   '''Parameters'''
   * {{code|startX}} - the x coordinate of the cell that will mark the upper left corner of the displayed area.
   * {{code|startY}} - the y coordinate of the cell that will mark the upper left corner of the displayed area.
   * {{code|endX}} - the x coordinate of the cell that will mark the lower right corner of the displayed area.
   * {{code|endY}} - the x coordinate of the cell that will mark the lower right corner of the displayed area
   * {{code|pixels}} - an optional parameter that if set to true (1) means the coordinates are measured in pixels. If set to false (0) the coordinates are measured in map cells. Defaults to true (1).
   * {{code|allPlayers}} - Optional: If set to true (1) and called from a trusted macro, all players views will be set. Defaults to 0


   |examples=
   Set the viewport of the current client such that it at least sees the corners of the area with the following CELL coordinates:
   <source lang="mtmacro" line>
   [h:setViewArea(0,0,30,20, 0)]
   </source>

   When the GM runs the macro change the viewport in PIXEL coordinates on ALL clients, else only on the current client:
   <source lang="mtmacro" line>
   [h:setViewArea(0, 0, 300, 200, 1, isGM())]
   </source>


   |also=
   {{func|getViewArea}}, {{func|getTokenY}}, {{func|goto}}, {{func|setZoom}}, {{func|getZoom}}.

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
