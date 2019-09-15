.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=restoreFoW
   |proposed=false
   |trusted=true
   |version=1.4.1.3
   |description=
   Resets all fog of war (FoW) for the map.

   |usage=
   <source lang="mtmacro" line>
   restoreFoW()
   restoreFoW(mapname)
   </source>

   This function resets all FoW for the current map or the indicated map if the optional map name is supplied. Duplicates the FoW reset available through '''Map Menu''' -> '''Restore Fog-of-War''' or when you import a new map sans dialog.

   '''Parameters'''
   {{param|mapname|Optional map name.}}

   |example=
   <source lang="mtmacro">
   <!-- Restore all Fog of War on current map -->
   [h: restoreFoW()]
   <!-- Restore all Fog of War on named map -->
   [h: restoreFoW("Skull Mountain")]
   </source>

   |also=
   [[Introduction_to_Lights_and_Sights#Fog_of_War|Introduction_to_Lights_and_Sights#Fog_of_War]], {{func|toggleFoW}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:FoW <Category:FoW>`__
