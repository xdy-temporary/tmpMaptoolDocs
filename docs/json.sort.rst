.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.sort
   |version=1.3b51
   |description=
   Used to sort JSON arrays. If the array contains only numbers, they are sorted numerically; otherwise, the values are sorted as strings alphabetically.

   |usage=
   <source lang="mtmacro" line>
   json.sort(array)
   </source>
   <source lang="mtmacro" line>
   json.sort(array, direction)
   </source>
   If you have a [[JSON_Array|JSON Array]] that contains [[JSON_Object|JSON Object]]s
   <source lang="mtmacro" line>
   json.sort(array, direction, key1, ..., keyN)
   </source>

   '''Parameters'''
   * {{code|array}} - The JSON array to sort.
   * {{code|direction}} - Defaults to {{code|"ascending"}}, acceptable values:
   ** {{code|"ascending"}}
   ** {{code|"descending"}}
   ** {{code|"ascend"}}
   ** {{code|"descend"}}
   ** {{code|"asc"}}
   ** {{code|"desc"}}
   ** {{code|"a"}}
   ** {{code|"d"}}
   * {{code|key1, ..., keyN}} - The keys in the [[JSON_Object|JSON Object]]s contained within the [[JSON_Array|JSON Array]] used for sorting. All [[JSON_Object|JSON Object]]s must contain these fields.

   |examples=
   Sorting a [[JSON_Array|JSON Array]] containing numbers.
   <source lang="mtmacro" line>
   [json.sort("[1,4,5,6,2,1,9,20,1]")]
   </source>

   Produces {{code|[1,1,1,2,4,5,6,9,20]}}

   Sorting a [[JSON_Array|JSON Array]] containing strings.
   <source lang="mtmacro" line>
   [json.sort("['Hero', 'Dragon', 'Elf', 'Wolf', 'Mage', 'Eagle', 'Troll']")]
   </source>

   Produces {{code|["Dragon","Eagle","Elf","Hero","Mage","Troll","Wolf"]}}

   Sorting a mixture of numbers and strings (all will be treated as string).
   <source lang="mtmacro" line>
   [json.sort("['Hero', 3, 'Elf', 'Wolf', 100, 'Eagle', 'Troll']")]
   </source>

   Produces {{code|[100,3,"Eagle","Elf","Hero","Troll","Wolf"]}}

   Sorting objects by a single string key
   <source lang="mtmacro" line>
   [h:vals = '[ {name:"Hero", HP:10}, 
                {name:"Wolf", HP:5}, 
                {name:"Mage", HP:20}, 
                {name:"Troll", HP:15}, 
                {name:"Eagle", HP:5} ]'] 
   [json.sort(vals, "a", "name")]
   </source>

   Produces 

   {{code|[{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Mage","HP":20},{"name":"Troll","HP":15},{"name":"Wolf","HP":5}]}}

   Sorting objects by a single numeric key
   <source lang="mtmacro" line>
   [h:vals = '[ {name:"Hero", HP:10}, 
                {name:"Wolf", HP:5}, 
                {name:"Mage", HP:20}, 
                {name:"Troll", HP:15}, 
                {name:"Eagle", HP:5} ]'] 
   [json.sort(vals, "a", "HP")]
   </source>

   Produces 

   {{code|[{"name":"Wolf","HP":5},{"name":"Eagle","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]}}

   Sorting objects by a two keys, first HP then Name.
   <source lang="mtmacro" line>
   [h:vals = '[ {name:"Hero", HP:10}, 
                {name:"Wolf", HP:5}, 
                {name:"Mage", HP:20}, 
                {name:"Troll", HP:15}, 
                {name:"Eagle", HP:5} ]'] 
   [json.sort(vals, "a", "HP", "name")]
   </source>

   Produces 

   {{code|[{"name":"Eagle","HP":5},{"name":"Wolf","HP":5},{"name":"Hero","HP":10},{"name":"Troll","HP":15},{"name":"Mage","HP":20}]}}

   [[Category:JSON_Function|Category:JSON Function]]
   }}
