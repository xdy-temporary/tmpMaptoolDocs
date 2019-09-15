.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=explode
   |description=
   Generates random numbers to emulate dice rolls; returns the total of a dice roll where dice that are rolled at maximum value are rolled again with the new roll added to the old. There is no limit to the total that that can be returned by this function, but the odds of each individual number decreases as the total increases past the number of {{code|sides}}. 

   |usage=
   <source lang="mtmacro" line>
   explode(times, sides)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}

   |examples=
   Roll a twenty-sided dice.
   <source lang="mtmacro" line>
   [t: explode(1, 20)]
   </source>
   Returns a number that is usually between {{code|1}} and {{code|20}}, with the possibility of the maximum value being higher than {{code|20}}.

   Roll five ten-sided dice, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [t: explode(DiceTimes, DiceSides)]
   </source>
   Returns a number than is usually between {{code|5}} and {{code|50}}, with the possibility of the maximum value being higher than {{code|50}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
