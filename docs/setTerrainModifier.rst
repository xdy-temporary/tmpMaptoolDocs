.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTerrainModifier
   |trusted=true
   |version=1.5.2
   |description=
   Set the Terrain Modifier for the named Token or for the Current Token if no name is given.

   |usage=
   <source lang="mtmacro" line>
   setTerrainModifier(mod)
   setTerrainModifier(mod, token)
   </source>
   '''Parameters'''
   {{param|mod|A floating point number.}}
   {{param|token|Optional token name.}}

   |example=
   Set the Terrain Modifier to 2.0 for the current token.

   <source lang="mtmacro" line>
   [r: tmod = setTerrainModifier(2.0)]
   </source>
   '''Returns:'''
   <source lang="mtmacro" line>
   2.0
   </source>

   |also=
   {{func|getTerrainModifier}}

   }}

`Category:Token Function <Category:Token_Function>`__
