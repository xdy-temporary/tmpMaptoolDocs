.. contents::
   :depth: 3
..

The variable *token.init* holds the value of the token's initiative when
the token is present in the Initiative Panel. Note that *token.init* is
only valid for tokens that are added to the Initiative Panel (querying
*token.init* when the token is not in the Initiative Panel will return
an error).

Usage
=====

To set a token's *token.init* value, do the following:

.. code:: mtmacro
   :number-lines:

   [token.init=value]

where *value* is a number.

Examples
========

After adding the token to the Initiative Panel (either by right-clicking
on the token and selecting **Add to Initiative**, or by using the
`addToInitiative() <Macros:Functions:addToInitiative>`__ function), you
can set the token's initiative via a macro such as the following:

.. code:: mtmacro
   :number-lines:

   [h:token.init = 1d20 + initBonus]

where *initBonus* is assumed to be a variable passed to the initiative
macro, or a `token property <Token:token_property>`__ of the token being
added. The new initiative value will appear in the initiative panel next
to the token name.

.. _related_pages:

Related Pages
=============

-  `Initiative Panel <Initiative:initiative_panel>`__
-  `token.initHold <token.initHold>`__

`Category:Special Variable <Category:Special_Variable>`__
