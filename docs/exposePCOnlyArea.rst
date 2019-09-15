.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   | name=exposePCOnlyArea
   | version=1.3b76
   |trusted=true
   | description=
   Clears Fog of War (FOW) where PC tokens can see and establishes/restores FOW everywhere they cannot.  This works the same as the hotkey Meta-Shift-O.  Note that the keystroke may be different for locales other than U.S. English.

   This function is often used in combination with the [[onTokenMove|onTokenMove]] event.
   | usage=
   <source lang="mtmacro">
   exposePCOnlyArea()
   exposePCOnlyArea(mapname)
   </source>

   '''Parameters'''
   {{param|mapname|Optional map name }}

   |example=
   <source lang="mtmacro" line>
   <!-- Expose areas that can be seen by PC tokens on current map. -->
   [h: exposePCOnlyArea()]
   <!-- Expose areas that can be seen by PC tokens on named map. -->
   [h: exposePCOnlyArea("Cliffs of Insanity")]
   </source>

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:FoW <Category:FoW>`__
