.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=reroll
   |description=
   Generates random numbers to emulate dice rolls; returns a dice roll similar to {{func|roll}} with the difference being that each dice rolled that is lower than the {{code|minimum}} parameter is rerolled until it is at least the {{code|minimum}}.

   |usage=
   <source lang="mtmacro" line>
   reroll(times, sides, minimum)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}
   {{param|minimum|The lowest number a dice rolled can return without being rerolled.}}

   |examples=
   Roll five ten-sided dice, rerolling any dice rolled lower than five.
   <source lang="mtmacro" line>
   [t: reroll(5, 10, 5)]
   </source>
   Returns a number that is between {{code|25}} and {{code|50}}.

   Roll five ten-sided dice, rerolling any dice rolled lower than five, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [h: DiceMinimum = 5]
   [t: roll(DiceTimes, DiceSides, DiceMinimum)]
   </source>
   Returns a number than is between {{code|25}} and {{code|50}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
