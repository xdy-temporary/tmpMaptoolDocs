.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bitwiseor
   |description=Performs a bitwise 'or' operation of the number arguments by taking the binary representation of each of the numbers and performing the logical or operation on each of the bits.

   '''Logical "or" Table'''
   {{{!}}
   {{!}}Bit1 {{!}}{{!}} Bit2 {{!}}{{!}}  Result
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1
   {{!}}-
   {{!}}align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1
   {{!}}}

   |usage=
   <source lang="mtmacro" line>
   [h: val = bor(num, num, ...)]
   [h: val = btwiseor(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: bor(1,0)]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: bor(1,1)]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: bor(0,0)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: bor(2, 4]
   </source>
   Returns 6.
   2 in binary is 010 and 4 in binary is 100, so a bitwise or of these two values is 110 which is 6 in decimal.

   <source lang="mtmacro" line>
   [r: band(20, 12)]
   </source>
   Returns 4.      
   20 in binary is 10100 and 12 in binary is 01100, the bitwise 'and' of these values is 00100 in binary which is 4 in decimal.
   }}

`Category:Logical Function <Category:Logical_Function>`__
