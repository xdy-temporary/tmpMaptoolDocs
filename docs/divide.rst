.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=divide
   |description=Divides the first number by the second number, and then divides that result by the third number --if present-- and so on for all the numbers passed to the function.

   |usage=
   <source lang="mtmacro" line>
   [h: props = divide(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: divide(4, 2)]
   </source>
   Returns 2.

   <source lang="mtmacro" line>
   [r: divide(24, 2, 2)]
   </source>
   Returns 6.
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
