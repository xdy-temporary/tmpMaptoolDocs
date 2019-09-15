.. contents::
   :depth: 3
..

The variable *token.visible* controls the visibility of the token to
players during a game. The variable can take two values, 0 (not visible)
or 1 (visible to players). This is equivalent to the "Visible to
players" option on the right-click menu for tokens.

Examples
========

.. _getting_token_visibility:

Getting Token Visibility
------------------------

.. code:: mtmacro
   :number-lines:

   [token.visible]

Will return 1 if the token is currently "Visible to players," and 0 if
it is not.

.. _setting_token_visibility:

Setting Token Visibility
------------------------

.. code:: mtmacro
   :number-lines:

   [token.visible = 0]

Will set *token.visible* to 0 - *e.g.*, making the token invisible to
players. A more useful approach might be:

.. code:: mtmacro
   :number-lines:

   [token.visible = 1 - token.visible]

This creates a "toggle" macro that will alternate *token.visible*
between its two possible values each time the button is clicked.

.. _related_pages:

Related Pages
=============

`Category:Special Variable <Category:Special_Variable>`__
