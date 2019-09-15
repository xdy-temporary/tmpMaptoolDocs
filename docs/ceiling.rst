.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=ceiling
   |description=Returns the number passed in if it is an integer, otherwise it returns the number rounded up to the next integer.

   |usage=
   <source lang="mtmacro" line>
   [h: val = ceil(num)]
   [h: val = ceiling(num)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: ceil(10)]
   </source>
   Returns 10.

   <source lang="mtmacro" line>
   [r: ceil(1.2)]
   </source>
   Returns 2.

   <source lang="mtmacro" line>
   [r: ceil(-1.2)]
   </source>
   Returns -1.
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
