.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=drop
   |description=
   Generates random numbers to emulate dice rolls; returns the total of a dice roll that ignores a certain number of the lowest dice rolled.

   |usage=
   <source lang="mtmacro" line>
   drop(times, sides, ignore)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}
   {{param|ignore|The number of lowest rolls that are ignored when totaling the roll.}}

   |examples=
   Roll ten twenty-sided dice, ignoring the lowest five rolls.
   <source lang="mtmacro" line>
   [t: drop(10, 20, 5)]
   </source>
   Returns a number that is between {{code|5}} and {{code|100}}, with a high average.

   Roll five ten-sided dice ignoring the lowest two rolls, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [h: DiceIgnore = 2]
   [t: drop(DiceTimes, DiceSides, DiceIgnore)]
   </source>
   Returns a number than is between {{code|3}} and {{code|30}}, with a high average.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
