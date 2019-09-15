.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= getViewArea
   |version=1.5.0
   |description=
   Returns the limits of the visible area of the map window, given in either pixels or cell coordinates depending on the first parameter. The result is in a ";" delimited String as default or can be configured by setting the delimiter or using Json.

   |usage=
   <source lang="mtmacro" line>
   getViewArea()
   getViewArea(pixels)
   getViewArea(pixels, delim)
   </source>

   '''Parameters'''
   * {{code|pixels}} - if set to true (1) means the returned coordinates are measured in pixels. If set to false (0) the returned coordinates are measured in map cells. Defaults to {{code|true}}.
   * {{code|delim}} - if set to "json" means the returned coordinates are defined in JSON style. Otherwise a String property list is returning using {{code|delim}} as a delimiter. Defaults to {{code|;}}.

   |examples=
   Get the viewport dimensions of the current client:
   <source lang="mtmacro" line>
   [r: getViewArea()] <!-- Default pixels -->
   [r: getViewArea(0)] <!-- in Grid Cells -->
   [r: getViewArea(1)] <!-- in Pixels -->
   [r: getViewArea(0, "json")] <!-- Cells as JSON -->
   [r: getViewArea(1, "json")] <!-- Pixels as JSON -->
   [r: getViewArea(0, ",")] <!-- Cells as "," separated String properties: -->
   [r: getViewArea(1, ";")] <!-- Pixels as ";" separated String properties: -->
   </source>

   Output:
   <source lang="mtmacro" line>
   startX=0; startY=0; endX=886; endY=616 
   startX=0; startY=0; endX=17; endY=12 
   startX=0; startY=0; endX=886; endY=616 
   {"startX":0,"startY":0,"endX":886,"endY":616} 
   {"startX":0,"startY":0,"endX":886,"endY":616} 
   startX=0, startY=0, endX=886, endY=616 
   startX=0; startY=0; endX=886; endY=616
   </source>

   |also=
   {{func|setViewArea}}, {{func|goto}}, {{func|setZoom}}, {{func|getZoom}}. 

   |change=
   {{change|1.5.1|fix the output of the function as it was incorrectly formatted, now the pixels parameter correctly defaults to true, you can use a delimiter to define output format}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
