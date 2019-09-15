.. contents::
   :depth: 3
..

The variable *token.gm_name* allows programmatic querying and setting of
the token's `GM Name <Token:GM_Name>`__ (the second text field in the
screenshot of the Edit Token dialog).

*token.gm_name* is only a valid expression in a trusted macro.

.. figure:: Edittoken-name-and-label.jpg
   :alt: Image:Edittoken-name-and-label.jpg

   Image:Edittoken-name-and-label.jpg

Examples
========

.. _getting_the_token_gm_name:

Getting the Token GM Name
-------------------------

.. code:: mtmacro
   :number-lines:

   [h:secretName=token.gm_name]
   GM's Name: [secretName]

Outputs the value of *token.gm_name*.

.. _setting_the_token_gm_name:

Setting the Token GM Name
-------------------------

.. code:: mtmacro
   :number-lines:

   [h:token.gm_name = "Soldier"]

Sets the value of *token.gm_name* to "Soldier."

.. _related_pages:

Related Pages
=============

-  `token.name <token.name>`__
-  `token.label <token.label>`__

`Category:Special Variable <Category:Special_Variable>`__
