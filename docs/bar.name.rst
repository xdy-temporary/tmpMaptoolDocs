.. contents::
   :depth: 3
..

The *bar.[bar_name]* variable permits the getting and setting of the
`token bar <Token:bar>`__ value (and the corresponding image displayed
on the token) programmatically. Token bars are one, two, or multi-image
graphical elements displayed on a token that are used (typically) to
visually indicate the status of consumable or expendable items or
character traits (such as Hit Points, Ammunition, Health, or the like).

Bars, like `token states <Token:state>`__, are configured via the
Campaign Properties dialog and are specific to the campaign in which
they exist. In the screenshot shown below, the green-on-black line
across the top of the token is a token bar.

.. figure:: Bar-example.jpg
   :alt: Image:Bar-example.jpg

   Image:Bar-example.jpg

Usage
=====

.. code:: mtmacro
   :number-lines:

   [bar.[bar_name] = value]

Sets the value of the token bar named *bar_name* to the desired value.
*bar_name* is set when the bar is created, and may be any name, provided
it contains no spaces or special characters except the underscore.
*Value* must be a number between 0 and 1.

Examples
========

.. code:: mtmacro
   :number-lines:

   [h: HP = HP - DamageTaken]
   [h: bar.Health = HP / MaxHP]

Sets the value of *bar.Health* to the result of *HP / MaxHP*.

Notes
=====

Two functions, `setBar() <Macros:Functions:setBar>`__ and
`getBar() <Macros:Functions:getBar>`__ also exist to get and set the
value of the token bar.

.. _related_pages:

Related Pages
=============

-  `List of Special
   Variables <Macros:Variables:list_of_special_variables>`__
-  `Token Bar
   Functions <Macros:Functions:list_of_functions_by_area#Token_Bars>`__

`Category:Special Variable <Category:Special_Variable>`__
