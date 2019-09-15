.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herostun
   |description=
   Generates random numbers to emulate dice rolls; acts like a standard {{func|roll}} with the difference being that a hidden variable is tracked, which can then be returned using {{func|herobody}}. This hidden variable is calculated by adding {{code|2}} for each dice that is rolled at maximum value, {{code|0}} for each dice that is rolled at minimum value, and {{code|1}} for each dice that is rolled at neither minimum, nor maximum value. 

   |usage=
   <source lang="mtmacro" line>
   herostun(times, sides)
   </source>
   <source lang="mtmacro" line>
   hero(times, sides)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}

   |examples=
   Roll a twenty-sided dice, and return the {{func|herobody}} result as well.
   <source lang="mtmacro" line>
   [t: herostun(1, 20)] - [t: herobody(1, 20)
   </source>
   Returns a number that is between {{code|1}} and {{code|20}} for the herostun roll, and a number between {{code|0}} and {{code|2}} for the herobody roll.

   Roll five ten-sided dice, and return the {{func|herobody}} result as well, using variables.
   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [t: herostun(DiceTimes, DiceSides)] - [t: herobody(DiceTimes, DiceSides)]
   </source>
   Returns a number than is between {{code|5}} and {{code|50}} for the herostun roll, and a number between {{code|0}} and {{code|10}} for the herobody roll.

   |also=
   Used in conjunction with {{func|herobody}}<br>
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
