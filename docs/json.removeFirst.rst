.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.removeFirst
   |proposed=false
   |trusted=false
   |version=1.4.0.3
   |description=
   Is similar to {{func|json.difference}} but will only remove the first occurrence of a match.

   |usage=
   <source lang="mtmacro" line>
   json.removeFirst(array1, array2)
   </source>

   '''Parameters'''
   {{param|array1|A JSON array.}}
   {{param|array2|A JSON array.}}

   Compares the two arrays and removes the first element from the first array matching an element in the second.

   |examples=
   <source lang="mtmacro" line>
   [json.removeFirst('[2,2,4,5,6,6,4]', '[2,6]')]
   </source>
   '''Outputs:'''
   <pre>  [2,4,5,6,4]</pre>
   Difference between {{func|json.removeFirst}} and {{func|json.difference}}.
   <source lang="mtmacro" line>
   [h: a1 = '[1,2,2,2,3,3,4,5,6,6]']
   [h: a2 = '[2,4,6]']
   [r: json.difference(a1,a2)]
   <!-- a1 has been modified - reset -->
   [h: a1 = '[1,2,2,2,3,3,4,5,6,6]']
   [r: json.removeFirst(a1,a2)]
   </source>
   '''Outputs:'''
   <pre>  [1,3,5]
     [1,2,2,3,3,5,6]</pre>
   |also=
   [[Introduction_to_JSON_Datatypes|Introduction to JSON Datatypes]], {{func|json.difference}}
   [[Category:JSON_Function|Category:JSON Function]]
   }}
