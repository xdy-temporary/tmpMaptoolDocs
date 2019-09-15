.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.rolls
   |proposed=false
   |trusted=false
   |version=1.4.0.5
   |description=
   Rolls the dice expression the requested number of times and returns a JSON Array with the result.

   |usage=
   <source lang="mtmacro" line>
   json.rolls(roll, dim1)
   json.rolls(roll, dim1, dim2)
   </source>

   '''Parameters'''
   {{param|roll|A string containing a dice roll expression.}}
   {{param|dim1|The dimension of the returned array.}}
   {{param|dim2|Optional: The second dimension for a two dimensional array.}}

   This function takes 2 or 3 parameters and returns a json array
   json.rolls(roll, dim1, dim2) => returns a json array with the rolls performed

   ''Example:''<source lang="mtmacro" line>
   {json.rolls("3d6", 6)} => [ 11, 7, 15, 8, 10, 13 ]
   </source>

   ''Example:''
   The three parameter version returns a two dimensional array
   <source lang="mtmacro" line>
   {json.rolls("3d6", 6, 4)} => [ [ 11, 13, 11, 13 ], [ 8, 11, 17, 10 ], [ 8, 11, 14, 11 ], [ 6, 8, 13, 6 ], [ 6, 11, 8, 10 ], [ 10, 7, 17, 11 ] ]
   </source>

   |also=
   [[Introduction_to_JSON_Datatypes|Introduction to JSON Datatypes]], {{func|json.objrolls}}
   [[Category:JSON_Function|Category:JSON Function]]
   }}
