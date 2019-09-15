.. contents::
   :depth: 3
..

The variable *token.label* allows programmatic querying and setting of
the token's `Label <Token:Token_label>`__ (the third text field in the
screenshot of the Edit Token dialog).

.. figure:: Edittoken-name-and-label.jpg
   :alt: Image:Edittoken-name-and-label.jpg

   Image:Edittoken-name-and-label.jpg

Examples
========

.. _getting_the_token_label:

Getting the Token Label
-----------------------

.. code:: mtmacro
   :number-lines:

   Token Name: [token.label]

Outputs the value of *token.label*.

.. _setting_the_token_label:

Setting the Token Label
-----------------------

.. code:: mtmacro
   :number-lines:

   [h:token.label = "Random Passerby"]

Sets the value of *token.label* to "Random Passerby".

.. _related_pages:

Related Pages
=============

-  `token.gm_name <token.gm_name>`__
-  `token.name <token.name>`__

`Category:Special Variable <Category:Special_Variable>`__
