.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=keep
   |description=
   Generates random numbers to emulate dice rolls; returns the total of a dice roll only counting a specified number of the highest rolls.

   |usage=
   <source lang="mtmacro" line>
   keep(times, sides, highDice)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}
   {{param|highDice|The number of highest dice that should be kept, the rest are discarded.}}

   |examples=
   Roll five ten-sided dice, keeping the two highest rolls.
   <source lang="mtmacro" line>
   [t: keep(5, 10, 2)]
   </source>
   Returns a number than is between {{code|2}} and {{code|20}}, with a high average.

   Roll five ten-sided dice, keeping the two highest rolls, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [h: DiceKeep = 2]
   [t: keep(DiceTimes, DiceSides, DiceKeep)]
   </source>
   Returns a number than is between {{code|2}} and {{code|20}}, with a high average.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
