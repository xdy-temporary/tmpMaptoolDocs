.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getZoom
   |version=1.4
   |description=
   Returns the current zoom level of the viewport in percentage, where 1 (=100%) is the default. This is the same number as what you find at the bottom of the Maptool window.

   |usage=
   <source lang="mtmacro" line>
   getZoom()
   </source>

   '''Parameters'''
   None.

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
   {{func|setZoom}},
   {{func|getTokenX}},
   {{func|getTokenY}},
   {{func|goto}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
