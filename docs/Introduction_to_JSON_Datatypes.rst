.. contents::
   :depth: 3
..

JSON stands for JavaScript Object Notation, which is kind of a fancy way
of saying the way you define objects in JavaScript -- technically only a
subset. Wait a minute I hear you say, "this is MapTool Macros not
JavaScript". Which of course is correct, but JSON has become common
enough that it is used in places other than JavaScript to define data.

MapTool macros have two different data types for JSON, `JSON
Objects <JSON_Object>`__ and `JSON Arrays <JSON_Array>`__, which I will
refer to as just objects and arrays from this point.

The following is a brief description of what arrays and objects are, if
you are still not sure after reading it don't worry, read on and
hopefully it will become clearer.

Arrays hold "lists" of data values. If you are familiar with the other
data structures in MapTool macro script arrays are analogous to string
lists.

Objects hold "key", "value" pairs, you will often hear this type of data
structure referred to either Map, Dictionary, Hash, Assosiative Array
depending on what other computer languages you are used to. If you are
familiar with the other data structures in MapTool macro script objects
are analogous to string property lists.

So if you want to keep a list of things you use an array, if you want to
keep a list of things that are key=blah type data you use an object.

First I will show you an example of how these structures look like in
JavaScript so you will have an idea of what they "look" like, then I can
show you an example on how you can use them to store data. Don't try
typing these into MapTool just yet, all the examples in this section are
how you would do it in JavaScript, so you understand how it looks and
get a feel for it, in `Using JSON Datatypes in
Macros <Using_JSON_Datatypes_in_Macros>`__ I will go show you how to use
JSON objects and arrays in your macros.

An array is enclosed in and has commas separating the values, strings
are enclosed in or . An empty array

.. code:: javascript
   :number-lines:

   empty = []

An array that contains the words , , , and

.. code:: javascript
   :number-lines:

   test = ["this", "is", "a", "test"]

An array that contains the values ,,,,

.. code:: javascript
   :number-lines:

   test = [4,5,12,10,1]

An object is enclosed in and has key : value separated by commas. For
the value strings are enclosed in or , for the key if it's a valid
identifier it does not have to be enclosed in or but you can if you
want. If you are unsure it's always safe just to use quotes around the
key.

So an empty object is

.. code:: javascript
   :number-lines:

   empty =  {}

An object that contains = =

.. code:: javascript
   :number-lines:

   person = {
       "first name" : "Fred",
       "last name" : "Flintstone"
   }

There is no reason it has to be on multiple lines, I just did that to
make it easier to read, the following is just as valid

.. code:: javascript
   :number-lines:

   person = { "first name" : "Fred", "last name" : "Flintstone" }

If you are familiar with the current `String Lists <String_List>`__ and
`String Property Lists <String_Property_List>`__ you may at this point
in time be asking what does this give me that they don't? Lets have a
look at the differences so far.

**Arrays vs String Lists** In string lists you have to specify a
delimiter, this delimiter -- which defaults to you can not have this
value in the data in the string list. For arrays the delimiter is always
but since the string values are also in quotes you can use the delimiter
in the data. For example:

.. code:: javascript
   :number-lines:

   test = ["This, is, a, test", "bah"]

Is only 2 elements in the array "This, is, a test" and "bah".

**Objects vs String Property Lists** This same things that were
mentioned in Arrays vs String Lists apply here too. In String Property
lists you can not use the delimiter or the character in your data. For
objects you can, for example.

.. code:: javascript
   :number-lines:

   person = {
       "first name" : "Fred",
       "last name" : "Flintstone",
       "address" : "Somewhere; around here => "
   }

**Embedded objects and arrays** With string lists you can embed property
lists within it, and you can also embed string lists within property
lists, but you have to be careful that none of the data in the inner
property list is a delimiter in the string list, or none of the data in
the inner string list is a delimiter in the property list.

So if you had a property list inside a string list, then the values in
the property list can not contain commas (or what ever you have set the
delimiter to if it is not the default). If you had a string lists inside
of property lists then you could not have ; (or what ever delimiter you
have specified) in the string list. And when you try to go a level
deeper it gets harder, and all in all its very prone to error.

JSON objects and arrays don't have the above problems.

First embedding an array inside another array:

.. code:: javascript
   :number-lines:

   test = [1, 2, 3, 
       ["a", "b", "c"],
    4, 5, 6]

And you can have arrays within arrays within arrays:

.. code:: javascript
   :number-lines:

   test = [1, 2, 3, 
       ["a", "b", "c",
           ["z", "x", "y"]
       ],
    4, 5, 6]

Again, there is no need to place it in separate lines but it makes it
clearer than if I wrote

.. code:: javascript
   :number-lines:

   test = [1, 2, 3, ["a", "b", "c", ["z", "x", "y"] ], 4, 5, 6]

Similar can be done with Objects.

An object within an object:

.. code:: javascript
   :number-lines:

   person = {
       "first name" : "Fred",
       "last name" : "Flintstone", 
       "address": { 
           "street": "301 Cobblestone Way",
           "city": "Bedrock"
       }
   }

Or

.. code:: javascript
   :number-lines:

   person = {
       "first name" : "Fred",
       "last name" : "Flintstone", 
       "address": { 
           "street": {
               number: 301,
               name: "Cobblestone Way"
           },
           "city": "Bedrock"
       }
   }

Again you could place it on one line like below, but its easier to
understand it on several lines

.. code:: javascript
   :number-lines:

   person = { "first name" : "Fred", "last name" : "Flintstone", "address": { "street": { number: 301, name: "Cobblestone Way" }, "city": "Bedrock" } }

You can place JSON objects in arrays such as:

.. code:: javascript
   :number-lines:

   people = [
       {
           "first name" : "Fred",
           "last name" : "Flintstone", 
           "address": { 
               "street": {
                   number: 301,
                   name: "Cobblestone Way"
               },
               "city": "Bedrock"
           }
       },
       {
           "first name" : "Barny",
           "last name" : "Rubble", 
           "address": { 
               "street": {
                   number: 303,
                   name: "Cobblestone Way"
               },
               "city": "Bedrock"
           }
   ]

You can also have arrays inside objects:

.. code:: javascript
   :number-lines:

   person = {
       "first name" : "Fred",
       "last name" : "Flintstone", 
       "address": { 
           "street": {
               number: 301,
               name: "Cobblestone Way"
           },
           "city": "Bedrock"
       },
       "family": ["Wilma", "Pebbles"]
   }

`Category:Tutorial <Category:Tutorial>`__
