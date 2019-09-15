.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=countsuccess
   |description=
   Generates random numbers to emulate dice rolls; returns the count of dice rolls that are above a certain target number.

   |usage=
   <source lang="mtmacro" line>
   countsuccess(times, sides, target)
   </source>
   <source lang="mtmacro" line>
   success(times, sides, target)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}
   {{param|target|The number that a dice needs to be equal to or higher to be considered a success.}}

   |examples=
   Roll twenty ten-sided dice, and return the number that are above five.
   <source lang="mtmacro" line>
   [t: countsuccess(20, 10, 5)]
   </source>
   Returns a number that is between {{code|0}} and {{code|20}}, which is the number of dice that rolled higher than {{code|5}}.

   Roll twelve six-sided dice, and return the number that are above three, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 12]
   [h: DiceSides = 6]
   [h: DiceSuccess = 3]
   [t: countsuccess(DiceTimes, DiceSides, DiceSuccess)]
   </source>
   Returns a number than is between {{code|0}} and {{code|12}}, which is the number of dice that rolled higher than {{code|3}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
