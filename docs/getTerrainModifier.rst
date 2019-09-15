.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTerrainModifier
   |trusted=true
   |version=1.5.2
   |description=
   Gets the Terrain Modifier for the named Token or for the Current Token if no name is given.

   |usage=
   <source lang="mtmacro" line>
   getTerrainModifier()
   getTerrainModifier(token)
   </source>
   '''Parameters'''
   {{param|token|Optional token name.}}

   |example=
   Get the Terrain Modifier for the named token:

   <source lang="mtmacro" line>
   [r: tmod = getTerrainModifier("Sticky Floor Tile")]
   </source>

   '''Output:'''
   <source lang="mtmacro" line>
   2.0
   </source>

   |also=
   {{func|setTerrainModifier}}

   }}

`Category:Token Function <Category:Token_Function>`__
