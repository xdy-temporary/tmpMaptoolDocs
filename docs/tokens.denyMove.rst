.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{code|tokens.denyMove}}

You can use this variable in the event to cancel the movement made.

usage
=====

.. code:: mtmacro
   :number-lines:

   <!-- @onTokenMove -->
   <!-- cance movement if condition -->
   [h, if(condition): tokens.denyMove = 1]

`Category:Special Variable <Category:Special_Variable>`__
