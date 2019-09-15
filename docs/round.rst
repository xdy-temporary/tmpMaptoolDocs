.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=round
   |description=Returns the rounded value of a number to    specified precision     (number of digits after the decimal point).    precision  can be zero (default).

   |usage=
   <source lang="mtmacro" line>
   [h: result = round(value, precision)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: round(1.45)]
   </source>
   Returns 1

   <source lang="mtmacro" line>
   [r: round(1.45, 1)]
   </source>
   Returns 1.5

   <source lang="mtmacro" line>
   [r: round(1.44,1)]
   </source>
   Returns 1.4
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
