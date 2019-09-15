.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=absolutevalue
   |description=Returns the absolute value of a number. The absolute value of a number is the number without the sign.

   |usage=
   <source lang="mtmacro" line>
   [h: val = absolutevalue(num)]
   </source>
   You can use the following shorthand for this function:
   <source lang="mtmacro" line>
   [h: val = abs(num)]
   </source>

   |examples=
   ====Negative Number====
   <source lang="mtmacro" line>
   [r: absolutevalue(-3)]
   </source>
   Returns:<source lang="mtmacro" line start=2>3</source>


   ====Positive Number====
   <source lang="mtmacro" line>
   [r: abs(4)]
   </source>
   Returns:<source lang="mtmacro" line start=2>4</source>


   ====Decimal Number====
   <source lang="mtmacro" line>
   [r: abs(3.4)]
   </source>
   Returns:<source lang="mtmacro" line start=2>3.4</source>

   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
