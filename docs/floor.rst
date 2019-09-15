.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=floor
   |description=Returns the number padded in if it is an integer, otherwise the number is rounded down to the nearest smaller integer and that value is returned.

   |usage=
   <source lang="mtmacro" line>
   [h: result = floor(num)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: floor(2)]
   </source>
   Returns 2.

   <source lang="mtmacro" line>
   [r: floor(1.2)]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: floor(-1.2)]
   </source>
   Returns -2.
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
