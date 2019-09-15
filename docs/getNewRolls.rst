.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getNewRolls
   |trusted=false
   |version=1.5.2
   |description=
   Returns an array of all the raw, i.e. unmodified, dice rolls since the last call to {{func|getNewRolls}}.

   |usage=
   <source lang="mtmacro" line>
   getNewRolls()
   </source>
   '''Parameters'''
   {{param|none|Takes no parameters.}}

   |example=
   Make some dice rolls and show the individual rolls at each step.

   <source lang="mtmacro" line>
   Roll 1d10: [e: 1D10+2]<br>
   Get New Rolls: [r: getNewRolls()]<br>
   Get Rolled: [r: getRolled()]<br>
   Roll 3d6 minimum 2: [e: 3D6L2]<br>
   Get New Rolls: [r: getNewRolls()]<br>
   Get Rolled: [r: getRolled()]</source>

   '''Output:'''
   <source lang="mtmacro" line>
    Roll 1d10: « 1D10+2 = 3 + 2 = 5 »
    Get New Rolls: [3]
    Get Rolled: [3]
    Roll 3d6 minimum 2: « 3D6L2 = 10 »
    Get New Rolls: [5,3,1]
    Get Rolled: [3,5,3,1]
   </source>

   Remember that it returns all the new die rolls since the last time it was called.
   <source lang="mtmacro" line>
   Roll 1: [e: 3d6]<br>
   [r: getNewRolls()]<br>
   Roll 2: [e: 3d6]<br>
   Roll 3: [e: 3d6]<br>
   [r: getNewRolls()]
   </source>
   '''Output'''
   <source lang="mtmacro" line>
   Roll 1: « 3d6 = 16 »
   [5,6,5]
   Roll 2: « 3d6 = 17 »
   Roll 3: « 3d6 = 6 »
   [5,6,6,3,2,1]
   </source>

   |also=
   {{func|clearRolls}} {{func|getRolled}}

   }}

`Category:Dice Function <Category:Dice_Function>`__
