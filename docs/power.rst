.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=power
   |version=1.3b36
   |description=
   Returns a {{code|number}} raised to the power of {{code|2}}, or raised to a specific ''exponent''.

   |usage=
   <source lang="mtmacro" line>
   power(num)
   </source>
   <source lang="mtmacro" line>
   power(num, exp)
   </source>
   <source lang="mtmacro" line>
   pow(num)
   </source>
   <source lang="mtmacro" line>
   pow(num, exp)
   </source>
   '''Parameters'''
   * {{code|num}} - the ''base number'' used to perform the operation.
   * {{code|exp}} - the ''exponent'' used in the operation.

   |examples=
   '''Example 1:''' Use {{code|power()}} to raise {{code|5}} to the power of {{code|2}}:
   <source lang="mtmacro" line>
   [r: power(5)]
   </source>
   '''Returns:''' {{code|25}}

   '''Example 2:''' Use {{code|pow()}} to raise {{code|5}} to the power of {{code|3}}:
   <source lang="mtmacro" line>
   [r: pow(5, 3)]
   </source>
   '''Returns:''' {{code|125}}

   |also=
   [[wp:Exponentiation|Exponentiation]], [[ln|ln()]]
   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
