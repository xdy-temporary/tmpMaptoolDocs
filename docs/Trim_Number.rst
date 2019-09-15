.. contents::
   :depth: 3
..

| ''' *Requires MapTool 1.3b56* '''
| The following is a user defined function that allows you to trim any
  trailing zeros from a floating point number(a number with decimal
  places). It also allows you to truncate the decimal places to a
  certain length and round any truncated decimal places in a certain
  direction.

Usage
=====

.. code:: mtmacro
   :number-lines:

   trimNumber(number)

.. code:: mtmacro
   :number-lines:

   trimNumber(number, length)

.. code:: mtmacro
   :number-lines:

   trimNumber(number, length, direction)

**Parameters:**

Macros
======

Place the following macros on the same library token(or on different
library tokens if you're know what you're doing and what to change).

.. raw:: html

   <hr>

**onCampaignLoad**

.. code:: mtmacro

   [defineFunction("trimNumber", "trimNumber@this", 1)]

.. raw:: html

   <hr>

| 

.. raw:: html

   <hr>

**trimNumber**

.. code:: mtmacro

   [assert(argCount() != 0, "trimNumber() requires at least one parameter.")]
   [assert(argCount() <= 3, "trimNumber() accepts a maximum of three parameters.")]
   [NumberToTrim = arg(0)]
   <!-- Set truncation depth -->
   [if(argCount() >= 2), code:
   {
       [TruncationDepth = power(10, arg(1))]
   };{
       [TruncationDepth = power(10, 10)]
   }]
   <!-- Set rounding method -->
   [if(argCount() == 3), code:
   {
       [RoundingMethod = substring(arg(2), 0 , 1)]
   };{
       [RoundingMethod = 0]
   }]
   <!-- Perform trim -->
   [switch(RoundingMethod):
       case "u": NumberToTrim = ceiling(NumberToTrim*TruncationDepth)/TruncationDepth;
       case "d": NumberToTrim = floor(NumberToTrim*TruncationDepth)/TruncationDepth;
       default: NumberToTrim = round(NumberToTrim*TruncationDepth)/TruncationDepth
   ]
   [macro.return = NumberToTrim]

.. raw:: html

   <hr>

| 

Examples
========

.. code:: mtmacro

   [r: trimNumber(1.125000)]

Returns

.. code:: mtmacro

   [r: trimNumber(1.125000, 2)]

Returns

.. code:: mtmacro

   [r: trimNumber(1.124000, 2)]

Returns

.. code:: mtmacro

   [r: trimNumber(1.123000, 2, "up")]

Returns

.. code:: mtmacro

   [r: trimNumber(1.128000, 2, "down")]

Returns

`Category:Cookbook <Category:Cookbook>`__