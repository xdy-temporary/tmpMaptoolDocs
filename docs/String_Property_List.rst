.. contents::
   :depth: 3
..

A string property list is a delimited string containing multiple
key-value pairs in the format value1; var2{{=}}value2;..."}}

For example:

.. code:: mtmacro
   :number-lines:

   [h: stringPropertyList="var1=foo; var2=bar; var3=baz;"]

String property lists are zero-based (*i.e.*, the first item in a string
property list is item ). When a key-value pair is extracted from a
string property list using one of the available `String
Functions <:Category:String_Function>`__ that work with string property
lists, the value of the pair is considered a string, and must be
converted to or evaluated to a number to perform numeric computations.

The default delimiter in a string property list is the semicolon (),
however, the `String Functions <:Category:String_Function>`__ that work
with string property lists permit the use of alternate delimiters.

The `String Property List
Functions <:Category:String_Property_List_Function>`__ only work with
the default delimiter.

String property lists may be stored in a `token
property <Token_Property>`__.

`Category:Variable Type <Category:Variable_Type>`__
