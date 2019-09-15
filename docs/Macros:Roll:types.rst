.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Macros:Roll:types}}

.. _roll_types_and_options:

[]/{} Roll Types and Options
============================

Text that you type into MapTool or execute from a `macro
button <Macro_Button>`__ is scanned for [ ] and { } blocks. The text
within these blocks is evaluated and the output from this evaluation is
placed into the string in its place.

{ } Rolls
---------

When the text is contained within { } then the text is evaluated and the
output copied in its place without any special formatting. For example
{2 + 2} produces |Image:Brace2Plus2.png‎|

.. _rolls_1:

[ ] Rolls
---------

Text that is within [ ] is evaluated, the output from [ ] is inserted
with a tool tip that displays the details of the evaluation -- the tool
tip can be displayed by leaving the mouse pointer over the result. For
example [2 + 2] produces

.. figure:: 2Plus2ToolTip.png
   :alt: Image:2Plus2ToolTip.png

   Image:2Plus2ToolTip.png

There are also several options that can be used within [ ] to change the
formatting. Options are specified after the [ and the option string is
terminated with a ':'. If you have more than one option then need to
separate them with a ',' eg [opt1, opt2: ...], if there are any
arguments for an option they are enclosed within (). All options are
case insensitive, so [opt: ...] is the same [OPT: ...].

.. _hidden_rolls:

[ ] Hidden Rolls
----------------

**[h: ]**, **[hide: ]**, **[hidden: ]** evaluates the text after the ':'
but completely discards the output. This is useful for setting variables
or other similar tasks where you want to change something but not
display any output.

If a chat message would appear empty because everything in it is hidden
from the player, the message is not displayed.

.. _expanded_rolls:

[ ] Expanded Rolls
------------------

**[e: ]**, **[expanded: ]** evaluates the text after the ':' and
displays the detailed output of the evaluation. [e: 2 + 2 ] would
display.

.. figure:: 2Plus2Expanded.png
   :alt: Image:2Plus2Expanded.png

   Image:2Plus2Expanded.png

.. _result_rolls:

[ ] Result Rolls
----------------

**[r: ]**, **[result: ]** evaluates the text after the ':' and displays
the plain output without any formatting or tool tips, the result is the
same as using { }. [r: 2 + 2] would display.

.. figure:: 2Plus2Result.png
   :alt: Image:2Plus2Result.png

   Image:2Plus2Result.png

.. _unformatted_rolls:

[ ] Unformatted Rolls
---------------------

**[u: ]**, **[unformatted: ]** evaluates the text after the ':' and
displays the detailed output without coloring or tool tips. [u: 2 + 2 ]
would display.

.. figure:: 2Plus2Unformatted.png
   :alt: Image:2Plus2Unformatted.png

   Image:2Plus2Unformatted.png

.. _tool_tip_rolls:

[ ] Tool Tip Rolls
------------------

**[t: ]**, **[tooltip: ]** evaluates the text after the ':' and displays
the result with a tool tip that displays the details of the evaluation
-- the tool tip can be displayed by leaving the mouse pointer over the
result. For example [t: 2 + 2] produces.

.. figure:: 2Plus2T.png
   :alt: Image:2Plus2T.png

   Image:2Plus2T.png

You can also specify an argument for the tooltip option. If you specify
an argument then this argument is evaluated and displayed, the text
after the ':' is evaluated and used as the tool tip. [t("four"): 2 + 2]
produces.

.. figure:: 2Plus2T-Four.png
   :alt: Image:2Plus2T-Four.png

   Image:2Plus2T-Four.png

.. _related_pages:

Related Pages
=============

-  `Dice Expressions <Dice_Expressions>`__
-  `Roll Visibility Options <Macros:Roll:output>`__
-  `Branching and Looping Roll Options <Macros:Branching_and_Looping>`__

.. raw:: mediawiki

   {{Languages|Macros:Roll:types}}

.. |Image:Brace2Plus2.png‎| image:: Brace2Plus2.png‎
