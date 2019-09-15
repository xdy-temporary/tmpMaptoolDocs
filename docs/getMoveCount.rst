.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction

   | name=getMoveCount
   | version=1.3b76
   |trusted=true
   | description=
   Returns the token's last movement count in units.  The count takes movement metric into account, and thus works on gridless, hex, and square grids.  Two optional parameters allow you to set the function to return true/false (1/0) if there was fractional movement left over and the second toggles whether Terrain Modifiers for determining returned movement count.

   | usage=
   <source lang="mtmacro">
   getMoveCount()
   getMoveCount(fractionOnly)
   getMoveCount(fractionOnly,useTerrainMods)
   </source>
   '''Parameters'''
   {{param|fractionOnly|0 for normal count (default); 1 for fractional movement - only valid with 1-2-1 movement metric}}
   {{param|useTerrainMods|0 to ignore terrain modifiers when determining movement count; 1 to account for terrain modifiers (default)}}

   '''Fraction Only''' - Return value will be a 0 when there was an even number of diagonal movements and 1 for an odd number.  This should only be used with the ONE-TWO-ONE movement metric.

   |changes=
   * '''1.5.0''' - Added Fraction Only and Use Terrain Modifiers parameters.
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
