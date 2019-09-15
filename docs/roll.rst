.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=roll
   |description=
   Generates random numbers to emulate dice rolls. You may also think of this function as a method of generating a random number between {{code|times}} and {{code|times*sides}}.

   |usage=
   <source lang="mtmacro" line>
   roll(times, sides)
   </source>
   <source lang="mtmacro" line>
   dice(times, sides)
   </source>
   <source lang="mtmacro" line>
   d(times, sides)
   </source>
   '''Parameters'''
   {{param|times|The number of times to roll the dice.}}
   {{param|sides|The number of sides the dice possess.}}

   '''Note:'''

   The roll function does not keep track of the individual dice rolled. In other words their results are lost, just the total is kept. How to roll dice when individual dice matter is shown in the examples.


   |examples=

   '''Roll a twenty-sided dice'''

   <source lang="mtmacro" line>
   [t: roll(1, 20)]
   </source>
   Returns a number that is between {{code|1}} and {{code|20}}.


   '''Roll five ten-sided dice, using variables'''

   <source lang="mtmacro" line>
   [h: DiceTimes = 5]
   [h: DiceSides = 10]
   [t: roll(DiceTimes, DiceSides)]
   </source>
   Returns a number than is between {{code|5}} and {{code|50}}.


   '''Throw multiple dice'''

   ...and sort and sum the result. Note that roll() doesnt help with this. You have to roll individual dice and keep track yourself. Gladly MapTool does help with loops and listkeeping functions. 

   <source lang="mtmacro">
   [h: diceTimes = 5]
   [h: diceSides = 6]
   [h: listOfRolls = ""]
   [h: sum = 0]
   [h, count(diceTimes), code: {
       [h: r = roll(1, diceSides)]
       [h: sum = sum+r]
       [h: listOfRolls = listAppend(listOfRolls, r)]
   }]
   You rolled [r: listSort(listOfRolls, "N-")] = [r: sum].
   </source>
   Rolls 5 times a d6 and returns these as sorted list as well as the total.

   : '''See also''' {{roll|count}}, {{func|listAppend}} and {{func|listSort}}.
    

   |also=
   For another method of rolling dice, see [[Dice_Expressions|Dice Expressions]].

   }}

`Category:Dice Function <Category:Dice_Function>`__
