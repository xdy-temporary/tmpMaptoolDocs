.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=explodingSuccess
   |description=
   Generates random numbers to emulate dice rolls; returns the count of dice rolls that are above a certain number, while each individual dice rolled at maximum value will be rerolled with the new roll added to the old. There is no limit to the number of time that that an individual dice rolled can be rerolled by this function, but the odds of each individual number decreases as the total increases past the number of sides.

   |usage=
   <source lang="mtmacro" line>
   explodingSuccess(times, sides, target)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}
   {{param|target|The number that a dice needs to be equal to or higher to be considered a success(added to the count returned).}}

   |examples=
   Roll a twenty-sided dice, and returns {{code|1}} if rolled higher than {{code|30}}.
   <source lang="mtmacro" line>
   [t: explodingSuccess(1, 20, 30)]
   </source>
   Returns {{code|0}} or {{code|1}}; {{code|1}} is only returned if the twenty-sided dice rolls {{code|20}} and then is rerolled(exploded) with a result equal to or higher than {{code|10}}.

   Roll five ten-sided dice, and returns the number of dice that rolled higher than twenty, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [h: DiceTarget = 20]
   [t: explodingSuccess(DiceTimes, DiceSides, DiceTarget)]
   </source>
   Returns a number than is between {{code|0}} and {{code|5}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
