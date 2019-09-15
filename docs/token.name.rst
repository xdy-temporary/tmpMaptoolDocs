.. contents::
   :depth: 3
..

The variable *token.name* allows programmatic querying and setting of
the token's `Name <Token:Token_name>`__ (the first text field in the
screenshot of the Edit Token dialog).

.. figure:: Edittoken-name-and-label.jpg
   :alt: Image:Edittoken-name-and-label.jpg

   Image:Edittoken-name-and-label.jpg

Examples
========

.. _getting_the_token_name:

Getting the Token Name
----------------------

.. code:: mtmacro
   :number-lines:

   [h:charName=token.name]
   Token Name: [charName]

Outputs the value of *token.name*.

.. _setting_the_token_name:

Setting the Token Name
----------------------

.. code:: mtmacro
   :number-lines:

   [h:token.name = "Marok the Red"]

Sets the value of *token.name* to "Marok the Red."

.. _related_pages:

Related Pages
=============

-  `token.gm_name <token.gm_name>`__
-  `token.label <token.label>`__

`Category:Special Variable <Category:Special_Variable>`__
