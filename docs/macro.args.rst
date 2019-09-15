.. contents::
   :depth: 3
..

The variable *macro.args* holds the value of the argument passed to a
trusted macro via the `MACRO() <macro_(roll_option)>`__ roll option.
*macro.args* exists only within the macro that is called, and may be
manipulated like any variable in a macro.

Examples
========

.. _single_parameter:

1: Single parameter
-------------------

When a macro on a `library token <Token:library_token>`__ is called by
another macro, the calling macro may pass one argument to the called
macro:

.. _calling_macro:

Calling Macro
~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- Call the getDamage macro -->
   [h:damageDice="2d6"]
   [MACRO("getDamage@Lib:test"): damageDice]

.. _called_macro:

Called Macro
~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- getDamage Macro -->
   [h:damageRoll = eval(macro.args) + 9]
   You hit your target for [r:damageRoll] damage!

In the example above, *damageDice* is the argument being passed to the
macro **getDamage**, which resides on the **Lib:test** `library
token <Token:library_token>`__. Within the **getDamage** macro, the
variable is automatically generated and assigned the value of
*damageDice*.

It's important to note that only a single parameter can be passed to a
macro and that parameter appears in the variable. If more than a single
parameter needs to be sent to a macro, you may use string property
lists, a JSON array or object, or a . The first two techniques are
demonstrated below.

.. _a_multiple_parameters_using_string_property_list:

2A: Multiple parameters using String Property List
--------------------------------------------------

A string property list essentially bundles multiple values into a single
string which would then be split back apart inside the macro body.

.. _calling_macro_1:

Calling Macro
~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- Call the doDamage macro -->
   [h:damageDice="2d6"]
   [h:theToken = "Bobo Fett"]
   [MACRO("getDamage@Lib:test"): "Damage="+damageDice+"; Token="+theToken]

.. _called_macro_1:

Called Macro
~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- doDamage Macro -->
   [h:dmg   = getStrProp(macro.args, "Damage")]
   [h:tokid = getStrProp(macro.args, "Token")]
   You hit [r: tokid] for [r:dmg] damage!

.. _b_multiple_parameters_using_json_array:

2B: Multiple parameters using JSON Array
----------------------------------------

The second way to pass multiple parameters is to use a `JSON
Array <JSON_Array>`__ or `JSON Object <JSON_Object>`__.

Using a JSON data type passes multiple values as a single unit. When
using JSON data types, there will be a single parameter coming into the
macro but because it's either an array or an object you can retrieve
individual fields quite easily.

As the is being passed as the first parameter in this next code block,
it's creating an empty `JSON Array <JSON_Array>`__ and then appending
two new values to it.

.. _calling_macro_using_json_array:

Calling Macro using JSON Array
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- Call the doDamage macro -->
   [h:damageDice="2d6"]
   [h:theToken = "Bobo Fett"]
   [h:jsonData = json.append("[]", damageDice, theToken)]
   [MACRO("getDamage@Lib:test"): jsonData]

.. _called_macro_using_json_array:

Called Macro using JSON Array
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- doDamage Macro -->
   [h:dmg   = json.get(macro.args, 0)]
   [h:tokid = json.get(macro.args, 1)]
   You hit [r: tokid] for [r:dmg] damage!

.. _c_multiple_parameters_using_json_object:

2C: Multiple parameters using JSON Object
-----------------------------------------

Notice that in this next example, the is being passed as the first
parameter. This indicates to the function that we want a `JSON
Object <JSON_Object>`__.

.. _calling_macro_using_json_object:

Calling Macro using JSON Object
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- Call the doDamage macro -->
   [h:damageDice="2d6"]
   [h:theToken = "Bobo Fett"]
   [h:jsonData = json.set("{}", "Damage", damageDice, "Token", theToken)]
   [MACRO("getDamage@Lib:test"): jsonData]

.. _called_macro_using_json_object:

Called Macro using JSON Object
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: mtmacro
   :number-lines:

   <!-- doDamage Macro -->
   [h:dmg   = json.get(macro.args, "Damage")]
   [h:tokid = json.get(macro.args, "Token")]
   You hit [r: tokid] for [r:dmg] damage!

.. _see_also:

See Also
========

`macro.return <macro.return>`__,

`Category:Special Variable <Category:Special_Variable>`__
