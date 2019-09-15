.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{code|tokens.moveCount}}

You can use this variable in and events to find out how many tokens were
moved.

usage
=====

.. code:: mtmacro
   :number-lines:

   <!-- @onMultipleTokensMove -->
   <!-- cancel movement if more than one token was moved -->
   [h, if(tokens.moveCount>1): tokens.denyMove = 1]

`Category:Special Variable <Category:Special_Variable>`__
