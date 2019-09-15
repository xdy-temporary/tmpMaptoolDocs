.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bitwiseand
   |description=Performs a bitwise 'and' operation of the {number} arguments by taking the binary representation of each of the numbers and performing the logical and operation on each of the bits.

   '''Logical "and" Table'''
   {{{!}}
   {{!}}Bit1 {{!}}{{!}} Bit2 {{!}}{{!}}  Result
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 0
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 0
   {{!}}-
   {{!}}align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 1
   {{!}}}

   |usage=
   <source lang="mtmacro" line>
   [h: val = band(num, num, ...)]
   [h: val = bitwiseand(num, num, ...)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: band(1,0)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: band(1,1)]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: band(3, 5]
   </source>
   Returns 1.
   3 in binary is 011 and 5 in binary is 101, the bitwise 'and' of these values is 001 in binary which is 1 in decimal.

   <source lang="mtmacro" line>
   [r: band(20, 12)]
   </source>
   Returns 4.      
   20 in binary is 10100 and 12 in binary is 01100, the bitwise 'and' of these values is 00100 in binary which is 4 in decimal.
   }}

`Category:Logical Function <Category:Logical_Function>`__
