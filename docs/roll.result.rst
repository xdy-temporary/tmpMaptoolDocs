.. contents::
   :depth: 3
..

The special variable is used within the parameter of the roll option.

Examples
========

.. _example_mimicking_the_default_display:

Example Mimicking the Default Display
-------------------------------------

.. code:: mtmacro
   :number-lines:

   [h:AtkBonus=6]
   [h:AbilBonus=4]
   Attack Result: [t(roll.result): 1d20+AtkBonus+AbilBonus]

|Tooltip-rollresult-example.jpg| Evaluates , assigns that value to , and
then displays the final result with a tooltip containing the value of .

The parameter for the roll option is evaluated after the roll itself is
evaluated, so that is available for display.

.. _example_of_a_custom_tooltip_based_on_the:

Example of a Custom Tooltip Based on the 
-----------------------------------------

To illustrate how the order of evaluation can be useful, consider the
following short example:

.. code:: mtmacro
   :number-lines:

   [t( if(roll.result > 10, "Hit", "Miss") ): d20]

This example will display or depending on the result of the d20 roll,
and the tooltip when hovering over either word will be the actual
numeric result of the d20 roll.

.. _see_also:

See Also
========

.. raw:: mediawiki

   {{roll|tooltip}}

`Category:Special Variable <Category:Special_Variable>`__

.. |Tooltip-rollresult-example.jpg| image:: Tooltip-rollresult-example.jpg
