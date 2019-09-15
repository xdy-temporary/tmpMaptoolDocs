.. contents::
   :depth: 3
..

A string property list is a string in the format "item1, item2,
item3,..."

For example:

.. code:: mtmacro
   :number-lines:

   [h: stringList="foo, bar, baz"]

String lists are zero-based (*i.e.*, the first item in a string list is
item 0). The default delimiter in a string property list is the comma
(","), however, the `String Functions <:Category:String_Function>`__
that work with string lists allow for optional arguments to permit the
use of alternate delimiters.

String lists may be stored in a `Token Property <Token_Property>`__.

`Category:Variable Type <Category:Variable_Type>`__
