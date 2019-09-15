.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. _while_option:

WHILE Option
============

**Introduced**: Version 1.3.b46

| Repeatedly executes a statement until a condition becomes false.
| The default **separator** is . Some examples of other useful
  separators: *nothing* , *space* and *break* .

Usage
-----

.. code:: mtmacro
   :number-lines:

   [WHILE(condition): body]
   [WHILE(condition, separator): body]

Example
-------

.. code:: mtmacro
   :number-lines:

   [h:num = 10]
   [WHILE(num >= 0): num = num - 1]

Outputs *9,8,7,6,5,4,3,2,1*

.. _example_1:

Example
-------

This example demonstrates how to put multiple instructions inside a loop
using the block extension.

Note the use of the second parameter to to force a line break in the
HTML output. Also notice that putting text on separate lines does NOT
force the output on separate lines; the HTML element is needed for that.

.. code:: mtmacro
   :number-lines:

   [h: End = 5]
   [H: Num = 0]
   [WHILE(Num < End, "<br>"), CODE: {
       Number is [Num = Num + 1],
       Next will be [Num+1]
   }]

Outputs:

.. raw:: mediawiki

   {{code|Number is 1, Next will be 2<br>
   Number is 2, Next will be 3<br>
   Number is 3, Next will be 4<br>
   Number is 4, Next will be 5<br>
   Number is 5, Next will be 6}}

`Category:Roll Option <Category:Roll_Option>`__ `Category:Looping Roll
Option <Category:Looping_Roll_Option>`__
