.. contents::
   :depth: 3
..

The variable *token.halo* allows programmatic querying and setting of
the token's **Halo**, a colored border that, if set, appears around the
token. In the image below, the yellow border around the token is the
token's halo.

.. figure:: Token-halo.jpg
   :alt: Image:Token-halo.jpg

   Image:Token-halo.jpg

Examples
========

.. _getting_the_token_halo_color:

Getting the Token Halo Color
----------------------------

.. code:: mtmacro
   :number-lines:

   Halo color: [token.halo]

Outputs the hexadecimal value for the token halo color. In the case of
the example image above, it would output *#ffff00*.

.. _setting_the_token_halo_color:

Setting the Token Halo Color
----------------------------

.. code:: mtmacro
   :number-lines:

   [h:token.halo = "red"]

or

.. code:: mtmacro
   :number-lines:

   [h:token.halo = #ff0000]

Sets the color of the token.halo to red (or the hexadecimal value
*#ff0000*).

.. _removing_the_token_halo:

Removing the Token Halo
-----------------------

.. code:: mtmacro
   :number-lines:

   [h:token.halo="None"]

.. _color_names_and_standard_colors:

Color Names and Standard Colors
-------------------------------

The *token.halo* variable accepts the following named colors (if using a
named color, enclose the value in quotes):

-  Black
-  Green
-  Yellow
-  Orange
-  Red
-  Blue
-  Cyan
-  DarkGray
-  Magenta
-  Pink
-  White

The variable will also accept any hexadecimal color value. Hexadecimal
color values do not need to be enclosed in quotes.

`Category:Special Variable <Category:Special_Variable>`__
