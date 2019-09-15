===========================================
Introduction to JSON Datatypes - MapToolDoc
===========================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Introduction to JSON Datatypes
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         JSON stands for JavaScript Object Notation, which is kind of a
         fancy way of saying the way you define objects in JavaScript --
         technically only a subset. Wait a minute I hear you say, "this
         is MapTool Macros not JavaScript". Which of course is correct,
         but JSON has become common enough that it is used in places
         other than JavaScript to define data.

         MapTool macros have two different data types for JSON, `JSON
         Objects </rptools/wiki/JSON_Object>`__ and `JSON
         Arrays </rptools/wiki/JSON_Array>`__, which I will refer to as
         just objects and arrays from this point.

         The following is a brief description of what arrays and objects
         are, if you are still not sure after reading it don't worry,
         read on and hopefully it will become clearer.

         Arrays hold "lists" of data values. If you are familiar with
         the other data structures in MapTool macro script arrays are
         analogous to string lists.

         Objects hold "key", "value" pairs, you will often hear this
         type of data structure referred to either Map, Dictionary,
         Hash, Assosiative Array depending on what other computer
         languages you are used to. If you are familiar with the other
         data structures in MapTool macro script objects are analogous
         to string property lists.

         So if you want to keep a list of things you use an array, if
         you want to keep a list of things that are key=blah type data
         you use an object.

         First I will show you an example of how these structures look
         like in JavaScript so you will have an idea of what they "look"
         like, then I can show you an example on how you can use them to
         store data. Don't try typing these into MapTool just yet, all
         the examples in this section are how you would do it in
         JavaScript, so you understand how it looks and get a feel for
         it, in `Using JSON Datatypes in
         Macros </rptools/wiki/Using_JSON_Datatypes_in_Macros>`__ I will
         go show you how to use JSON objects and arrays in your macros.

         An array is enclosed in ``[ ]`` and has commas separating the
         values, strings are enclosed in ``"`` or ``'``. An empty array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     empty = []

         An array that contains the words ``"this"``, ``"is"``, ``"a"``,
         and ``"test"``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = ["this", "is", "a", "test"]

         An array that contains the values
         ``4``,\ ``5``,\ ``12``,\ ``10``,\ ``1``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = [4,5,12,10,1]

         An object is enclosed in ``{ }`` and has key : value separated
         by commas. For the value strings are enclosed in ``"`` or
         ``'``, for the key if it's a valid identifier it does not have
         to be enclosed in ``"`` or ``'`` but you can if you want. If
         you are unsure it's always safe just to use quotes around the
         key.

         So an empty object is

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     empty =  {}

         An object that contains ``first name`` = ``Fred`` ``last name``
         = ``Flintstone``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = {

               #. .. code-block:: none

                         "first name" : "Fred",

               #. .. code-block:: none

                         "last name" : "Flintstone"

               #. .. code-block:: none

                     }

         There is no reason it has to be on multiple lines, I just did
         that to make it easier to read, the following is just as valid

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = { "first name" : "Fred", "last name" : "Flintstone" }

         If you are familiar with the current `String
         Lists </rptools/wiki/String_List>`__ and `String Property
         Lists </rptools/wiki/String_Property_List>`__ you may at this
         point in time be asking what does this give me that they don't?
         Lets have a look at the differences so far.

         **Arrays vs String Lists** In string lists you have to specify
         a delimiter, this delimiter -- which defaults to ``,`` you can
         not have this value in the data in the string list. For arrays
         the delimiter is always ``,`` but since the string values are
         also in quotes you can use the delimiter in the data. For
         example:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = ["This, is, a, test", "bah"]

         Is only 2 elements in the array "This, is, a test" and "bah".

         **Objects vs String Property Lists** This same things that were
         mentioned in Arrays vs String Lists apply here too. In String
         Property lists you can not use the delimiter or the ``{{{1}}}``
         character in your data. For objects you can, for example.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = {

               #. .. code-block:: none

                         "first name" : "Fred",

               #. .. code-block:: none

                         "last name" : "Flintstone",

               #. .. code-block:: none

                         "address" : "Somewhere; around here => "

               #. .. code:: de2

                     }

         **Embedded objects and arrays** With string lists you can embed
         property lists within it, and you can also embed string lists
         within property lists, but you have to be careful that none of
         the data in the inner property list is a delimiter in the
         string list, or none of the data in the inner string list is a
         delimiter in the property list.

         So if you had a property list inside a string list, then the
         values in the property list can not contain commas (or what
         ever you have set the delimiter to if it is not the default).
         If you had a string lists inside of property lists then you
         could not have ; (or what ever delimiter you have specified) in
         the string list. And when you try to go a level deeper it gets
         harder, and all in all its very prone to error.

         JSON objects and arrays don't have the above problems.

         First embedding an array inside another array:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = [1, 2, 3, 

               #. .. code-block:: none

                         ["a", "b", "c"],

               #. .. code-block:: none

                      4, 5, 6]

         And you can have arrays within arrays within arrays:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = [1, 2, 3, 

               #. .. code-block:: none

                         ["a", "b", "c",

               #. .. code-block:: none

                             ["z", "x", "y"]

               #. .. code-block:: none

                         ],

               #. .. code:: de2

                      4, 5, 6]

         | 
         | Again, there is no need to place it in separate lines but it
           makes it clearer than if I wrote

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     test = [1, 2, 3, ["a", "b", "c", ["z", "x", "y"] ], 4, 5, 6]

         Similar can be done with Objects.

         An object within an object:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = {

               #. .. code-block:: none

                         "first name" : "Fred",

               #. .. code-block:: none

                         "last name" : "Flintstone", 

               #. .. code-block:: none

                         "address": { 

               #. .. code:: de2

                             "street": "301 Cobblestone Way",

               #. .. code-block:: none

                             "city": "Bedrock"

               #. .. code-block:: none

                         }

               #. .. code-block:: none

                     }

         Or

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = {

               #. .. code-block:: none

                         "first name" : "Fred",

               #. .. code-block:: none

                         "last name" : "Flintstone", 

               #. .. code-block:: none

                         "address": { 

               #. .. code:: de2

                             "street": {

               #. .. code-block:: none

                                 number: 301,

               #. .. code-block:: none

                                 name: "Cobblestone Way"

               #. .. code-block:: none

                             },

               #. .. code-block:: none

                             "city": "Bedrock"

               #. .. code:: de2

                         }

               #. .. code-block:: none

                     }

         Again you could place it on one line like below, but its easier
         to understand it on several lines

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = { "first name" : "Fred", "last name" : "Flintstone", "address": { "street": { number: 301, name: "Cobblestone Way" }, "city": "Bedrock" } }

         You can place JSON objects in arrays such as:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     people = [

               #. .. code-block:: none

                         {

               #. .. code-block:: none

                             "first name" : "Fred",

               #. .. code-block:: none

                             "last name" : "Flintstone", 

               #. .. code:: de2

                             "address": { 

               #. .. code-block:: none

                                 "street": {

               #. .. code-block:: none

                                     number: 301,

               #. .. code-block:: none

                                     name: "Cobblestone Way"

               #. .. code-block:: none

                                 },

               #. .. code:: de2

                                 "city": "Bedrock"

               #. .. code-block:: none

                             }

               #. .. code-block:: none

                         },

               #. .. code-block:: none

                         {

               #. .. code-block:: none

                             "first name" : "Barny",

               #. .. code:: de2

                             "last name" : "Rubble", 

               #. .. code-block:: none

                             "address": { 

               #. .. code-block:: none

                                 "street": {

               #. .. code-block:: none

                                     number: 303,

               #. .. code-block:: none

                                     name: "Cobblestone Way"

               #. .. code:: de2

                                 },

               #. .. code-block:: none

                                 "city": "Bedrock"

               #. .. code-block:: none

                             }

               #. .. code-block:: none

                     ]

         You can also have arrays inside objects:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code-block:: none

                     person = {

               #. .. code-block:: none

                         "first name" : "Fred",

               #. .. code-block:: none

                         "last name" : "Flintstone", 

               #. .. code-block:: none

                         "address": { 

               #. .. code:: de2

                             "street": {

               #. .. code-block:: none

                                 number: 301,

               #. .. code-block:: none

                                 name: "Cobblestone Way"

               #. .. code-block:: none

                             },

               #. .. code-block:: none

                             "city": "Bedrock"

               #. .. code:: de2

                         },

               #. .. code-block:: none

                         "family": ["Wilma", "Pebbles"]

               #. .. code-block:: none

                     }

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_JSON_Datatypes&oldid=2585"

