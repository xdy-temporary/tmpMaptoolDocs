.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= exposeFogAtWaypoints
   |trusted=true
   |version=1.4.1.8
   |description=
   Returns a string {{code|(Enabled/Disabled)}} indicating whether the '''Expose Fog At Waypoints''' option is set in the MapTool Map menu. This menu option toggles the setting for the currently displayed map.

   This setting affects when automatic exposure of Fog of War (FoW) will be performed after a token has been moved.  With it enabled, FoW will only be exposed at any waypoints set by the user along the tokens path plus the stopping point.  If not enabled, FoW will be exposed from every cell along the token's path.

   |usage=
   <source lang="mtmacro" line>
   exposeFogAtWaypoints()
   </source>
   '''Parameters'''
   None.

   |examples=
   <source lang="mtmacro" line>
   [h: empty = exposeFogAtWaypoints()]
   </source>

   '''Returns:'''  
   * Disabled - Option is disabled.
   * Enabled - Option is enabled.

   |also=
   {{func|exposeFOW}}, {{func|toggleFoW}}
   }}

`Category:FoW <Category:FoW>`__
