.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.unique
   |version=1.3b53
   |description=
   Returns a [[JSON_Array|JSON Array]] with each value that occurs in the source [[JSON_Array|JSON Array]] occurring only once. The relative order of the values in the array may not be preserved.


   |usage=
   <source lang="mtmacro" line>
   json.unique(array)
   </source>
   '''Parameters'''
   {{param|array|The [[JSON_Array|JSON Array]] to return only unique values from.}}

   |example=
   Lets say you have a [[JSON_Array|JSON Array]] that contains the following [[Token|Token]] names: {{code|["Hero", "Dragon"]}}, and you use {{code|{{func|getPCNames}}}} to return the names of
   the [[PC_Token|PC Token]]s, you could use the following code to generate a [[JSON_Array|JSON Array]] that contains the values in both [[JSON_Array|JSON Array]]s with no value present more than once.
   <source lang="mtmacro" line>
   [h: names1 = '["Hero", "Dragon"]']
   [h: names2 = getNPCNames()]
   [h: names = json.merge(names1, names2)]
   [r: json.unique(names)]
   </source>
   If {{code|{{func|getPCNames}}}} returns {{code|["Hero", "Sidekick", "Policeman"]}} then the
   result of the above code will be {{code|["Policeman","Sidekick","Hero","Dragon"]}}

   While the above example demonstrates the output of {{code|{{func|json.unique}}}} if you want to merge
   two or more arrays and get the unique values in one step you can use the {{code|{{func|json.union}}}}
   function.

   |also=
   {{func|json.merge}}
   {{func|json.union}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
