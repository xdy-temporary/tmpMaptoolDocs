.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setZoom
   |version=1.4
   |description=
   Sets the zoom level of the viewport in percentages, where 1 (=100%) is the default.

   |usage=
   <source lang="mtmacro" line>
   setZoom(z)
   </source>

   '''Parameters'''
   * {{code|z}} - The zoom level of the viewport (the current zoom level can be seen at the bottom of the maptool screen. You can also use {{func|getZoom}}. Note that this value is given in the numerical representation of %. E.g. to set zoom to 50% you give 0.5 as parameter.

   |examples=
   Zoom in by a factor 2
   <source lang="mtmacro" line>
   [h: z = getZoom()]
   [h: setZoom(2*z)]
   </source>
   Zoom in by one 10%
   <source lang="mtmacro" line>
   [h: z = getZoom()]
   [h: setZoom(z+0.1)]
   </source>
   Zoom out by 10%
   <source lang="mtmacro" line>
   [h: z = getZoom()]
   [h: setZoom(z-0.1)]
   </source>

   |also=
   {{func|moveToken}}, 
   {{func|getTokenY}},
   {{func|goto}},
   {{func|setViewArea}},
   {{func|getZoom}}.
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
