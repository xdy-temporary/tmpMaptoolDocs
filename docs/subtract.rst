.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=subract
   |description=
   Subtracts the second number from the first number. Then will continue by subtracting the third number (if any from this result), the function continues subtracting until all number arguments are exhausted.

   |usage=
   <source lang="mtmacro" line>
   [h: num = subtract(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
       [r: subtract(10, 2, 4)]
       [r: subtract(9, 10, 3)]
   </source>
   Returns 
       4
       -4
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
