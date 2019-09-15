.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herobody
   |description=
   Generates random numbers to emulate dice rolls; this is the partner function to {{func|herostun}}. The parameters used when calling this function must be exactly the same as the parameters used when calling {{func|herostun}}, and it must be called during the same macro as {{func|herostun}} or an error will result. Refer to {{func|herostun}} for full usage details.

   |usage=
   <source lang="mtmacro" line>
   herobody(times, sides)
   </source>
   '''Parameters'''
   {{param|times|The same {{code|times}} parameter that was used when calling {{func|herostun}}.}}
   {{param|sides|The same {{code|sides}} parameter that was used when calling {{func|herostun}}.}}

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
   Used in conjunction with {{func|herostun}}<br>
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
