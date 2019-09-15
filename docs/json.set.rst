.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.set
   |version=1.3b49
   |description=
   Sets the value in at the specified index in a [[JSON_Array|JSON Array]] or for the specified key in a [[JSON_Object|JSON Object]]. You can use an empty string ({{code|""}}) to represent a new [[JSON_Array|JSON Array]] or [[JSON_Object|JSON Object]].

   |usage=
   <source lang="mtmacro" line>
   newarr=json.set(jarr, [])
   </source>
   <source lang="mtmacro" line>
   newarr=json.set(jarr, index, value)
   </source>
   <source lang="mtmacro" line>
   newarr=json.set(jarr, index, value, ..., ...)
   </source>
   <source lang="mtmacro" line>
   newobj=json.set(jobj, key, value)
   </source>
   <source lang="mtmacro" line>
   newobj=json.set(jobj, key, value, ..., ...)
   </source>
   '''Parameters'''
   {{param|jarr|The [[JSON_Array|JSON Array]] that has an index's value set.}}
   {{param|index|The numeric index which has its value set.}}
   {{param|jobj|The [[JSON_Object|JSON Object]] that has a key's value set.}}
   {{param|key|The named key which has its value set.}}
   {{param|value|The content that is set to the {{code|index}} or {{code|key}}.}}

   '''Note:''' The {{code|index}} and {{code|value}} parameters or {{code|key}} and {{code|value}} parameters can be repeated in pairs.

   '''Note:''' {{code|newarr}} or {{code|newobj}} can be equal to {{code|jarr}} or {{code|jobj}}. In this case, the object/array will simply be updated.

   '''Note:''' The word "class" is a reserved word in JavaScript; it is therefore not possible to create a JSON object containing a ''key'' named "Class," "class," or any mix of upper- and lower-case. MapTool will ignore any instructions to set a JSON object key with that name.


   |example=
   <source lang="mtmacro" line>
     [json.set("{}", "a", 5)]
     [json.set("", "a", 5, "b", 8)]
     [json.set(json.fromList("1,3"), 0, 8)]
   </source>

   Returns
     {"a":5}
     {"a":5, "b":8}
     [8, 3]

   To save the new value in the [[JSON_Array|JSON Array]] or [[JSON_Object|JSON Object]] so that you can reference it later in a macro, you must set the array equal to the result of json.set().

   <source lang="mtmacro" line>
      [myArray = json.append("", 1, 2, 3)]
      [myArray = json.set(myArray, 0, 5)]
      [myArray]
   </source>

   Returns
      [1,2,3] 
      [5,2,3] 
      [5,2,3]

   |also=
   {{func|json.get}}
   }}

`Category:JSON Function <Category:JSON_Function>`__
