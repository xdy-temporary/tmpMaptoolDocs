.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.objrolls
   |proposed=false
   |trusted=false
   |version=1.4.0.5
   |description=
   Is similar to {{func|json.rolls}} but returns a JSON object.

   |usage=
   <source lang="mtmacro" line>
   json.objrolls(names, stat, rolls)
   </source>

   '''Parameters'''
   {{param|names|A JSON array containing the names to be used for each group.}}
   {{param|stat|A JSON array with the stat names.}}
   {{param|rolls|Either a single string containing a dice roll expression  or a JSON array of dice roll expressions.}}

   This will generate rolls for each stat in a group for each "name". Rolls is either a single string with a roll expression in which case every stat will use same roll expression, or a json array with a roll expression for each stat (so must be same size as stat).

   ''Example:''<source lang="mtmacro" line>
   {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",
           "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",
           "3d6"),2)}
   </source>

   <pre>code:{  "henchman1":   {
       "Str": 10,
       "Dex": 12,
       "Con": 10,
       "Int": 10,
       "Wis": 8,
       "Chr": 12
     },
          "henchman2":   {
       "Str": 11,
       "Dex": 10,
       "Con": 7,
       "Int": 13,
       "Wis": 9,
       "Chr": 7
     },
          "henchman3":   {
       "Str": 10,
       "Dex": 10,
       "Con": 10,
       "Int": 12,
       "Wis": 15,
       "Chr": 13
     }}

.. raw:: html

   </pre>

*Example:*

.. code:: mtmacro
   :number-lines:

   {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",
           "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",
           "['3d6+1', '3d6', '3d6', '3d6-2', '3d6', '2d6']"),2)}

::

   code:{  "henchman1":   {
       "Str": 11,
       "Dex": 12,
       "Con": 13,
       "Int": 8,
       "Wis": 10,
       "Chr": 11
     },
           "henchman2":   {
       "Str": 12,
       "Dex": 11,
       "Con": 12,
       "Int": 8,
       "Wis": 12,
       "Chr": 3
     },
           "henchman3":   {
       "Str": 12,
       "Dex": 13,
       "Con": 9,
       "Int": 8,
       "Wis": 13,
       "Chr": 7
     }}

\|also= `Introduction to JSON
Datatypes <Introduction_to_JSON_Datatypes>`__, }}

`Category:JSON Function <Category:JSON_Function>`__
