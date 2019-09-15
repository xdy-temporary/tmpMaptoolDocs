.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=fudge
   |description=
   Generates random numbers to emulate dice rolls; returns the total of a special Fudge dice roll. When these dice are rolled, the result is {{code|-1}}, {{code|0}}, or {{code|1}}, this function then sums up all of the dice rolled and returns that sum.

   |usage=
   <source lang="mtmacro" line>
   fudge(times)
   </source>
   <source lang="mtmacro" line>
   f(times)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}

   |examples=
   Roll ten special Fudge dice.
   <source lang="mtmacro" line>
   [t: fudge(10)]
   </source>
   Returns a number that is between {{code|-10}} and {{code|10}}.

   Roll five special Fudge dice, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [t: fudge(DiceTimes)]
   </source>
   Returns a number than is between {{code|-5}} and {{code|5}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
