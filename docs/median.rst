.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=median
   |description=
   Returns the [[wp:Median|Median]] of the numbers passed in. The median value is the value where half the numbers in the list are higher or equal to it and the other half are lower or equal to it. The median is calculated by sorting the list of numbers and picking the middle number if the list has an odd amount or averaging the two in the middle if there is an even amount. 

   |usage=
   <source lang="mtmacro" line>
   [h: av = median(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
       [r: median(3,6,2,2)]   
       [r: median(12, 23, 3, 102, 1)]
   </source>
   Returns 
       2.5
       12
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
