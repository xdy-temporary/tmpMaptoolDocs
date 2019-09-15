.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bitwisexor
   |description=Performs a bitwise 'exlusive or' operation of the number arguments by taking the binary representation of each of the numbers and performing the logical exclusive or operation on each of the bits.

   '''Logical " exclusive or" Table'''
   {{{!}}
   {{!}}Bit1 {{!}}{{!}} Bit2 {{!}}{{!}}  Result
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1
   {{!}}-
   {{!}}align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 0
   {{!}}}

   |usage=
   <source lang="mtmacro" line>
   [h: val = bxor(num, num, ...)]
   [h: val = bitwisexor(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: bxor(1,0)]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: bxor(1,1)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: bxor(0,0)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: bxor(2, 4]
   </source>
   Returns 6.
   2 in binary is 010 and 4 in binary is 100, so a bitwise xor of these two values is 110 which is 6 in decimal.

   <source lang="mtmacro" line>
   [r: bxor(6, 4)]
   </source>
   Returns 2.      
   6 in binary is 110 and 4 in binary is 100, so a bitwise xor of these two values is 010 which is 2 in decimal.
   }}

`Category:Logical Function <Category:Logical_Function>`__
