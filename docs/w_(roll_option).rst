.. contents::
   :depth: 3
..

.. _display_to_specific_player_option:

[ ] Display to Specific Player Option
=====================================

.. raw:: html

   <div>

• **Introduced in version 1.3.b58**

.. raw:: html

   </div>

**[w("name"): ]**, **[whisper("name"): ]** evaluates the text after the
':' but only displays the results to the specific named user, such as:

.. code:: mtmacro
   :number-lines:

   Everyone can see this [w("bob"): "but only Bob can see this"]

.. raw:: mediawiki

   {{roll|w}}

can also take more than one player name as an argument:

.. code:: mtmacro
   :number-lines:

   [w("Fred", "Joe"): d20]

It can also take a JSON list containing player names:

.. code:: mtmacro
   :number-lines:

   [h: names = json.fromList("Fred, Joe")]
   [w(names): d20]

This roll option may be combined with the , , , and options. Blank
messages will not be shown to a certain user if an entire message is
invisible to that user due to these roll options or the roll option.

`Category:Roll Option <Category:Roll_Option>`__ `Category:Display Roll
Option <Category:Display_Roll_Option>`__
