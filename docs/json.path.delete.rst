.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.path.delete
   |version=1.5.5
   |description=
   Returns a [[JSON_Array|JSON Array]] or [[JSON_Object|JSON Object]] with deleted elements. These deletions are specified through the path parameter. Additional information on how to specify the path is availabe [https://github.com/json-path/JsonPath here].

   |usage=
   <source lang="mtmacro" line>
   json.path.delete(json, path)
   </source>

   '''Parameters'''
   {{param|json|The json element to delete the value from.}}
   {{param|path|The path of the values.}}

   |examples=
   Suppose we have the following nested json:
   <source lang="mtmacro" line>
   [h:troll = json.set("{}", "name", "Troll", "HP", 75, "Attacks", json.append("Claw", "Bite"))]
   [h:orc = json.set("{}", "name", "Orc", "HP", 13, "Attacks", json.append("Sword", "Punch"))]
   [h:monsters = json.set("{}", "Troll", troll, "Orc", orc)]
   </source>

   To delete the "Punch" attack of the Orc, we could write

   <source lang="mtmacro" line>
   [r: json.path.delete(monsters, "Orc.Attacks.[1]")]
   </source>

   or, alternatively,

   <source lang="mtmacro" line>
   [r: json.path.delete(monsters, "Orc.Attacks[?(@ == 'Punch')]")]
   </source>

   Either statement return the json without the "Punch",

   <source lang="mtmacro" line>
   {"Troll":{"name":"Troll","HP":75,"Attacks":["Claw","Bite"]},"Orc":{"name":"Orc","HP":13,"Attacks":["Sword"]}}

.. raw:: html

   </source>

}}

`Category:JSON Function <Category:JSON_Function>`__
