.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=clearRolls
   |trusted=false
   |version=1.5.2
   |description=
   Clears the internal array that keeps track of the individual dice rolls for the current macro.

   |usage=
   <source lang="mtmacro" line>
   clearRolls()
   </source>
   '''Parameters'''
   {{param|none|Takes no parameters.}}

   |example=
   Clear the saved rolls after second time.

   <source lang="mtmacro" line>
   Roll 3d6: [e: 3D6]<br>
   Get New Rolls: [r: getNewRolls()]<br>
   Get Rolled: [r: getRolled()]<br>
   Roll 3d6 minimum 2: [e: 3D6L2]<br>
   Get New Rolls: [r: getNewRolls()]<br>
   Get Rolled: [r: getRolled()]<br>
   -- Clear Rolls --[h: clearRolls()]<br>
   Roll 3d6: [e: 3D6]<br>
   Get New Rolls: [r: getNewRolls()]<br>
   Get Rolled: [r: getRolled()]<br>
   </source>

   '''Output:'''
   <source lang="mtmacro" line>

   Roll 3d6: « 3D6 = 12 »
   Get New Rolls: [5,5,2]
   Get Rolled: [5,5,2]
   Roll 3d6 minimum 2: « 3D6L2 = 17 »
   Get New Rolls: [5,6,6]
   Get Rolled: [5,5,2,5,6,6]
   -- Clear Rolls --
   Roll 3d6: « 3D6 = 8 »
   Get New Rolls: [2,2,4]
   Get Rolled: [2,2,4]
   </source>

   |also=
   {{func|getNewRolls}} {{func|getRolled}}

   }}

`Category:Dice Function <Category:Dice_Function>`__
