.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getAllPlayerNames
   |trusted=true
   |version=1.3b48
   |description=Gets a [[Macros:string_list|string list]] containing the names of all the players that are connected.

   |usage=
   <source lang="mtmacro" line>
   getAllPlayerNames()
   getAllPlayerNames(delim)
   </source>

   If {{code|delim}} is specified then it is used to separate the values in the list; if it is not specified then it defaults to "{{code|,}}".  When {{code|delim}} is the string "{{code|json}}" the return value will be in the form of a [[JSON_Array|JSON Array]].

   |example=
   You can use the following code to print the names of all of the players that are connected.
   <source lang="mtmacro" line>
   Players Connected<br>
   [h: players = getAllPlayerNames()]
   [foreach(name, players, "<br>"): name]
   </source>
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
