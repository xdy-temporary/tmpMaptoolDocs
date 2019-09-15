.. contents::
   :depth: 3
..

The variable *macro.return* holds the value returned from a called macro
to the calling macro. Other than *macro.return*, a called variable
shares no other variables with the calling macro.

Examples
========

When a macro on a `library token <Token:library_token>`__ is called by
another macro, the called macro may return a value to the called macro
by assigning that value to the variable *macro.args*.

.. _calling_macro:

Calling Macro
-------------

The macro below calls a macro called **getDamage** on the `library
token <Token:library_token>`__ "Lib:combat", passing the variable
*damageDice* as an argument. It also sets

============================================= ==============================================================
Calling Macro                                 Called Macro
============================================= ==============================================================
.. code:: mtmacro                             .. code:: mtmacro
   :number-lines:                                :number-lines:
                                             
   [h:damageDice="2d6"]                          <!-- getDamage Macro -->
   [MACRO("getDamage@Lib:combat"):damageDice]    [h:returnData = ""]
   [h:damageProperties=macro.return]             [h:damageRoll = eval(macro.args) + 9]
   [h:varsFromStrProp(damageProperties)]         [h:damageType = "piercing"]
                                                 You hit your target for [r:damageRoll] damage!
                                                 [h:returnData=setStrProp(returnData,"damType", damageType)]
                                                 [h:returnData=setStrProp(returnData,"damage", damageRoll)]
                                                 [h:macro.return=returnData]
============================================= ==============================================================

In the example above, we assume that the **getDamage** macro was called
by another macro (for example, a token macro) and has received some
value in the form of *macro.args*. The statements in **getDamage** are
executed, and the final statement assigns the value of returnData to the
variable *macro.return*.

When execution of the **getDamage** macro is complete and control is
handed back to the calling macro, *macro.return* is also passed back to
the calling macro, where it can be manipulated like any other variable.

`Category:Special Variable <Category:Special_Variable>`__
