.. contents::
   :depth: 3
..

Introduced in version 1.5.0. The variable can be used to override the
behavior of the default function to continue execution instead of
halting.

Whenever you set to , any use of in a subsequently called macro will not
assert, but will trigger a return from the macro instead.

The variable must be in the variable scope where the assert should be
caught. It is not a general flag to turn off assert behavior, just
temporarily in the macro or variable scope where it's set.

Usage
=====

Set this variable to (default assert behavior) or (catch asserts).

.. code:: mtmacro
   :number-lines:

   [h: macro.catchAssert = 0]
   [h: macro.catchAssert = 1]

Examples
========

When a macro is called by another macro, the called macro may use to
cancel execution and show an error message. Usually all macro execution
would stop, so the calling macro would not continue. We can now override
that default behavior by *catching* the assert (it will still show the
error message).

.. _default_behaviour:

Default behaviour
-----------------

The macro below will only have "error occured" as output because the
default behavior is that any call to will stop the overall macro
execution. Whatever code is defined after the call to is not executed.

===============================================
Default assert Macro
===============================================
.. code:: mtmacro
   :number-lines:

   [h: resultText = "defaultValue"]
   [h: resultText = assert(0, "error occured")]
   [r: resultText]
===============================================

.. _catching_the_assert:

Catching the assert
-------------------

The macro below will output "error occured" and as the set to prevents
the call to from actually terminating execution. The example shows how
to set a default value for any return value of a function/macro that has
an call in it. The macro then re-enables the normal function of again by
setting to . As each macro has its own variable scope, this only affects
calls to within the current macro or calls to other macros from the
current macro. The exception is if the called macro shares the scope
with the calling macro, in which case the is ignored.

===============================================
Catching assert
===============================================
.. code:: mtmacro
   :number-lines:

   [h: macro.catchAssert = 1]
   [h: resultText = "defaultValue"]
   [h: resultText = assert(0, "error occured")]
   [r: resultText]
   [h: macro.catchAssert = 0]
===============================================

.. _catching_the_assert_with_nested_macro_calls:

Catching the assert with nested macro calls
-------------------------------------------

Same as in the above example, the calling macro below will output "error
occured" and because we activate deferred asserts (in anything that this
macro will call afterwards) with set to .

====================================================== ===================================
Called macro using an assert as function doSomething() Calling macro catching an assert
====================================================== ===================================
.. code:: mtmacro                                      .. code:: mtmacro
   :number-lines:                                         :number-lines:
                                                      
   [h: "this macro will do something and then assert"]    [h: macro.catchAssert= 1]
   [h: "... doing something"]                             [h: resultText = "defaultValue"]
   [h: assert(0, "error occured")]                        [h: resultText = doSomething()]
                                                          [r: resultText]
                                                          [h: macro.catchAssert= 0]
====================================================== ===================================

.. _see_also:

See also
--------

`assert() <assert>`__

.. _version_changes:

Version changes
---------------

.. raw:: mediawiki

   {{change|1.5.0|introduced macro.assertCatch}}

`Category:Special Variable <Category:Special_Variable>`__
