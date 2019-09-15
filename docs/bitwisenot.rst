.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bitwisenot
   |description=Performs a bitwise 'not' operation of the {number}. A bitwise not is performed by taking the binary representation of the {number} and performing a logical 'not' operation on each of these bits.

   '''Logical "not" Table'''
   {{{!}}
   {{!}}Bit {{!}}{{!}}  Result
   {{!}}-
   {{!}}align=center{{!}} 0 {{!}}{{!}} align=center{{!}} 1
   {{!}}-
   {{!}}align=center{{!}} 1 {{!}}{{!}} align=center{{!}} 0
   {{!}}}

       
   Unfortunately its not quite as simple as the table above makes it appear since number are a string of 32 (or more bits) so a 1 in binary is actually a 00000000000000000000000000000001 and a 0 is actually a 00000000000000000000000000000000 so the table is now.

           bnot of binary 00000000000000000000000000000000
                   is             11111111111111111111111111111111
           which is -1 in decimal

           bnot of binary 00000000000000000000000000000001 
           is             11111111111111111111111111111110
           which is -2 in decimal

   If you are unsure why the results are negative then you can get more information by reading [[wp:Twos_complement|Twos_complement]]

   |usage=
   <source lang="mtmacro" line>
   [h: val = bnot(num)]
   [h: val = bitwisenot(num)]
   </source>

   |examples=
   <source lang="mtmacro" line>
   [bnot(1)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: bnot(1)]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [r: bnot(12]
   </source>
   Returns -13.
   }}

`Category:Logical Function <Category:Logical_Function>`__
