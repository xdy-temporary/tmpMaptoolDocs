.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= getViewCenter
   |version=1.5.4
   |description=
   Returns the limits of the visible area of the map window, given in either pixels or cell coordinates depending on the first parameter. The result is in a ";" delimited String as default or can be configured by setting the delimiter or using JSON.

   |usage=
   <source lang="mtmacro" line>
   getViewCenter()
   getViewCenter(pixels)
   getViewCenter(pixels, delim)
   </source>

   '''Parameters'''
   * {{code|pixels}} - if set to true (1) means the returned coordinates are measured in pixels. If set to false (0) the returned coordinates are measured in map cells. Defaults to {{code|true}}.
   * {{code|delim}} - if set to "json" means the returned coordinates are defined in JSON style. Otherwise a String property list is returning using {{code|delim}} as a delimiter. Defaults to {{code|;}}.

   |examples=
   Get the viewport dimensions of the current client:
   <source lang="mtmacro" line>
   [r: getViewCenter()] <!-- Default pixels -->
   [r: getViewCenter(0)] <!-- in Grid Cells -->
   [r: getViewCenter(1)] <!-- in Pixels -->
   [r: getViewCenter(0, "json")] <!-- Cells as JSON -->
   [r: getViewCenter(1, "json")] <!-- Pixels as JSON -->
   [r: getViewCenter(0, ",")] <!-- Cells as "," separated String properties: -->
   [r: getViewCenter(1, ";")] <!-- Pixels as ";" separated String properties: -->
   </source>

   Output:
   <source lang="mtmacro" line>
   centerX=646; centerY=319;
   centerX=14; centerY=7;
   centerX=646; centerY=319;
   {"centerX":14,"centerY":7} 
   {"centerX":646,"centerY":319} 
   centerX=14, centerY=7;
   centerX=646; centerY=319,
   </source>

   |also=
   {{func|getViewArea}}, {{func|setViewArea}}, {{func|goto}}, {{func|setZoom}}, {{func|getZoom}}. 

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
