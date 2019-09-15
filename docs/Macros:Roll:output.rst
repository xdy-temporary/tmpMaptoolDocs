.. contents::
   :depth: 3
..

.. _roll_visibility_options:

Roll Visibility Options
=======================

.. _output_visibility:

Output Visibility
-----------------

These roll options control who is able to see the result of a given
roll.

-  **[s: ]**, **[self: ]** makes the roll visible only to the player who
   made the roll.
-  **[g: ]**, **[gm: ]** makes the roll visible only to GMs.
-  **[w("name"): ]**, **[whisper("name"): ]** makes the roll visible to
   the selected player.

These roll options can be combined to make a roll visible to multiple
people. If none of these options are used, output is visible to
everyone.

**[w(): ]** can also take more than one player name as an argument:

.. code:: mtmacro
   :number-lines:

   [w("Fred", "Joe"): d20]

It can also take a JSON list containing player names:

.. code:: mtmacro
   :number-lines:

   [h: names = json.fromList("Fred, Joe")]
   [w(names): d20]

If a chat message would appear empty because everything in it is hidden
from the player, the message is not displayed.

.. _tooltip_visibility:

Tooltip Visibility
------------------

These options control who can see the tooltip showing detailed roll
output. If the roll doesn't have a tooltip, these have no effect.

-  **[st: ]**, **[selftt: ]** makes the tooltip visible only to the
   player who made the roll.
-  **[gt: ]**, **[gmtt: ]** makes the tooltip visible only to GMs.

These options can be combined with each other and with the other output
options. If neither of these options are used, the tooltip is visible to
everyone.

.. _related_pages:

Related Pages
=============

-  `Roll Types and Options <Macros:Roll:types>`__
-  `Branching and Looping Roll Options <Macros:Branching_and_Looping>`__
