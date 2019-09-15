.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getRolled
   |trusted=false
   |version=1.5.2
   |description=
   Returns an array of all the raw, i.e. unmodified, dice rolls that have occurred within the current macro context.

   |usage=
   <source lang="mtmacro" line>
   getRolled()
   </source>
   '''Parameters'''
   {{param|none|Takes no parameters.}}

   |example=
   Roll some dice and observe the unmodified rolls.

   <source lang="mtmacro" line>
   Roll 1d10: [e: 1D10+2]<br>
   Get Rolled: [r: getRolled()]<br>
   Roll 3d6 minimum 2: [e: 3D6L2]<br>
   Get Rolled: [r: getRolled()]
   </source>

   '''Output:'''
   <source lang="mtmacro" line>
   Roll 1d10: « 1D10+2 = 9 + 2 = 11 »
   Get Rolled: [9]
   Roll 3d6 minimum 2: « 3D6L2 = 13 »
   Get Rolled: [9,6,5,1]
   </source>

   |also=
   {{func|clearRolls}} {{func|getNewRolls}}

   }}

`Category:Dice Function <Category:Dice_Function>`__
