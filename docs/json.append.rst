.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.append
   |version=1.3b49
   |description=
   Appends values to the end of a [[JSON_Array|JSON Array]]. An empty string ("") can be used to represent an empty [[JSON_Array|JSON Array]] to append the values to.

   |usage=
   <source lang="mtmacro" line>
   [h: jarr = json.append(jarr, value, ...)]
   </source>

   |example=
   <source lang="mtmacro" line>
     [h:a=json.fromList("a,1,g,4")][r: json.append(a, 55)]
     [r: json.append("", 1, 5, 8, 33)]
   </source>

   Returns
      ["a",1,"g",4,55]
      [1,5,8,33]
   }}

`Category:JSON Function <Category:JSON_Function>`__
