.. contents::
   :depth: 3
..

If you don't know JavaScript or JSON already I highly suggest you read
`Introduction to JSON Datatypes <Introduction_to_JSON_Datatypes>`__
first even though it is JavaScript based.

So how do you create `JSON Objects <JSON_Object>`__ and `JSON
Arrays <JSON_Array>`__ in MapTool macro script? Well the easy way if you
already know everything you want is to create it as a string. Lets
define a data structure that will hold the details for a weapon.

The weapon will be a gun which has the following details:

-  Number of shots before reload
-  Damage done
-  Attack penalty per shot (so more than one shot around has an attack
   penalty).

So if we were to define this in JavaScript we could just do it as

.. code:: javascript
   :number-lines:

   weapon = {
       "name": "Handgun",
       "shots": 6,
       "damage": "1d10"
   }

If you already know what your JSON object looks like defining it in
MapTool is not too different.

.. code:: mtmacro
   :number-lines:

   [r: weapon = '{
       "name": "Handgun",
       "shots": 6,
       "damage": "1d10"
   }']

If you copy and paste this into MapTool you will notice that the output
is returned on one line

.. code:: mtmacro
   :number-lines:

   [r: weapon = '{ "name": "Handgun", "shots": 6, "damage": "1d10" }']

This is because the chat window displays html and new line characters
are not displayed. If you wanted to see the carriage returns as you
typed them then you could do

.. code:: mtmacro
   :number-lines:

   <pre>
   [r: weapon = '{
       "name": "Handgun",
       "shots": 6,
       "damage": "1d10"
   }']
   </pre>

Which says the output is already preformatted so new line characters
will be displayed.

The above is well and good if you know what you want to store ahead of
time, but how do you create a JSON object based on user input or results
of a macro. For this you use .

So to create the above weapon you could use

.. code:: mtmacro
   :number-lines:

   [r: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10" )]

Where is an empty JSON object, for convenience can be used as the first
argument to to represent an empty object.

.. raw:: mediawiki

   {{func|json.set}}

takes an object as well a list of key and value pairs and returns a new
object with the specified keys set . **It is important to rememeber this
last bit, all of the json functions do not modify the object, instead
they create a new object with the changes.** For example

.. code:: mtmacro
   :number-lines:

   [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10" )]
   [h: weapon2 = json.set(weapon, "name", "Bigger Handgun")]
   [r: weapon] <br>
   [r: weapon2]

Displays

::

   {"name":"Handgun","shots":6,"damage":"1d10"}
   {"name":"Bigger Handgun","shots":6,"damage":"1d10"}

The original value in weapon has not been modified.

If you placed around the output you will notice that json.set() creates
the object on one line, not formatted nicely across multiple lines as it
was when we created it manually. If you want to "format" this nicely you
can use the command.

For example:

.. code:: mtmacro
   :number-lines:

   <pre>[r: json.indent('{"name":"Handgun","shots":6,"damage":"1d10"}', 4)]</pre>

Produces:

::

   {
       "name": "Handgun",
       "shots": 6,
       "damage": "1d10"
   }

Using JSON arrays is similar Lets to our weapon above, in this mythical
system that the gun belongs to you are able to fire all of the shots in
one round but each after the first has a two hit penalty. We can
represent this as an array with 6 elements (we will include the first
shot for simplicities sake even if it would always be 0).

.. code:: mtmacro
   :number-lines:

   [r: modifiers = '[0, 1, 3, 5, 8, 12]']

The function allows you to append items to the end of an array, if the
array is empty then it will create a new one.

If the input is an it is an empty array, for convenience also represents
an empty array. json.set() can be used on arrays but only to set a value
for an index, the array must already have that index.

For example if I wanted to change the 3rd index in the array above to 4
I could do

.. code:: mtmacro
   :number-lines:

   [h: modifiers = json.set(modifiers, 2, 4)

The value for index is because indexes in the array start at .

So given what we learned earlier you could add the modifiers to our
weapon object in the following way

.. code:: mtmacro
   :number-lines:

   [r: modifiers = '[0, 1, 3, 5, 8, 12]']
   [r: weapon = json.set(weapon, "modifiers", modifiers)]

Or you could do it as

.. code:: mtmacro
   :number-lines:

   [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10",
       "modifiers", "[0, 1, 3, 5, 8, 12]" )]
   <pre>[r: json.indent(weapon,4)]</pre>

Which will display

::

   {
       "name": "Handgun",
       "shots": 6,
       "damage": "1d10",
       "modifiers":     [
           0,
           1,
           3,
           5,
           8,
           12
       ]
   }

Of course if you know all the details up front you can create the whole
objects as before such as.

.. code:: mtmacro
   :number-lines:

   [r: weapon = '{
       "name" : "Handgun",
       "shots" : 6,
       "damage" : 1d10,
       "modifiers" : "[0, 1, 3, 5, 8, 12]"
   }']

The next question is now that we have all the information in a JSON
object or array how do we get it out when we need it?

To get things out of objects or arrays we use

So

.. code:: mtmacro
   :number-lines:

   [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10",
       "modifiers", "[0, 1, 3, 5, 8, 12]" )]
   Weapon Name: [r: json.get(weapon, "name")]<br>
   Damage: [r: json.get(weapon, "damage")] <br>
   Shots: [r: json.get(weapon, "shots")] <br>
   [h: modifiers = json.get(weapon, "modifiers")]
   Modifiers [r,c(json.get(weapon, "shots")): json.get(modifiers, roll.count)]

Which displays

::

   Weapon Name: Handgun 
   Damage: 1d10 
   Shots: 6 
   Modifiers 0, 1, 3, 5, 8, 12

You could also use to change the line that displays the modifiers to

.. code:: mtmacro
   :number-lines:

   Modifiers [r,c(json.length(modfiers)): json.get(modifiers, roll.count)]

But there is an easier way to loop through every value in the array and
that is using `foreach <foreach_(roll_option)>`__

.. code:: mtmacro
   :number-lines:

   Modifiers [r,foreach(val,modifiers): val]

json.length() and foreach can be used on JSON objects as well as arrays.
In this case json.length() returns the number of key/value pairs, and
foreach will loop through the keys in the object.

So using the above objects

.. code:: mtmacro
   :number-lines:

   [r: json.length(weapon)]

Displays .

and

.. code:: mtmacro
   :number-lines:

   [r,foreach(val,weapon): val]

Displays

::

   name, shots, damage, modifiers

`Category:Tutorial <Category:Tutorial>`__
