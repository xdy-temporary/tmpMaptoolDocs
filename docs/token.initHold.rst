.. contents::
   :depth: 3
..

The variable *token.initHold* is a binary variable that indicates
whether a token in the `Initiative
Panel <Initiative:initiative_panel>`__ is on hold, or is part of the
normal initiative cycle. *token.initHold* can take a value of 1 (token
is on hold) or 0 (token is not on hold).

Usage
=====

.. code:: mtmacro
   :number-lines:

   [token.initHold = value]

Where *value* is either 1 or 0.

Example
=======

.. code:: mtmacro
   :number-lines:

   [h:status=input(
       "hold|Yes,No|Put token on hold in initiative order?|RADIO|SELECT=0 ORIENT=H VALUE=STRING"
       )]
   [h:abort(status)]

   [h:token.initHold = if(hold=="Yes", 1, 0)]

Presents the following dialog using the
`input() <Macros:Functions:input>`__ function:

.. figure:: InitHold-example.jpg
   :alt: Image:InitHold-example.jpg

   Image:InitHold-example.jpg

and, based on the user's selection, sets *token.initHold* to either 1 or
0. When this macro is executed, the token's image or line in the
`Initiative Panel <Initiative:initiative_panel>`__ will be altered to
reflect its new status.

.. _related_pages:

Related Pages
=============

-  `Initiative Panel <Initiative:initiative_panel>`__
-  `token.init <token.init>`__

`Category:Special Variable <Category:Special_Variable>`__
