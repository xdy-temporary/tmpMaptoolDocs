.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.path.read
   |version=1.5.5
   |description=
   Returns the values in a nested [[JSON_Array|JSON Array]] or [[JSON_Object|JSON Object]] corresponding to the provided path. For detailed information on how to specify the path, please read the [https://github.com/json-path/JsonPath following document].

   |usage=
   <source lang="mtmacro" line>
   json.path.read(json, path)
   </source>

   '''Parameters'''
   {{param|json|The json element to get the values from.}}
   {{param|path|The path of the values.}}

   |examples=
   Suppose we have the following nested json:
   <source lang="mtmacro" line>
   [h:troll = json.set("{}", "name", "Troll", "HP", 75, "Attacks", json.append("Claw", "Bite"))]
   [h:orc = json.set("{}", "name", "Orc", "HP", 13, "Attacks", json.append("Sword", "Punch"))]
   [h:monsters = json.set("{}", "Troll", troll, "Orc", orc)]
   </source>

   To access the value of the first weapon of the Orc, we can type

   <source lang="mtmacro" line>
   [json.path.read(monsters, "Orc.Attacks.[0]")]
   </source>

   which returns "Sword".

   If we instead wanted to return an array with the attacks of every monster, we could type

   <source lang="mtmacro" line>
   [r: json.path.read(monsters, ".Attacks")]
   </source>

   which would return [["Claw","Bite"],["Sword","Punch"|"Claw","Bite"],["Sword","Punch"]].

   Inline filters are also supported, so that if we want the name of the monsters with > 30 HPs, we can type

   <source lang="mtmacro" line>
   [r: json.path.read(monsters, ".[?(@.HP > 30)].name")]
   </source>

   which returns ["Troll"].

   }}

`Category:JSON Function <Category:JSON_Function>`__
