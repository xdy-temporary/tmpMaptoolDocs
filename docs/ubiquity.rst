.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=ubiquity
   |description=
   Generates random numbers to emulate dice rolls; returns the total of a special Ubiquity dice roll. When these dice are rolled, the result is {{code|0}} or {{code|1}}, this function then sums up all of the dice rolled and returns that sum.

   |usage=
   <source lang="mtmacro" line>
   ubiquity(times)
   </source>
   <source lang="mtmacro" line>
   u(times)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}

   |examples=
   Roll ten special Ubiquity dice.
   <source lang="mtmacro" line>
   [t: ubiquity(10)]
   </source>
   Returns a number that is between {{code|0}} and {{code|10}}.

   Roll five special Ubiquity dice, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [t: ubiquity(DiceTimes)]
   </source>
   Returns a number than is between {{code|0}} and {{code|5}}.

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
