.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getAllMapNames
   |version=1.3b55
   |trusted=true
   |description=
   Returns the names of all of the maps as either a [[String_List|String List]] or [[JSON_Array|JSON Array]]. 

   |usage=
   <source lang="mtmacro" line>
   getAllMapNames()
   getAllMapNames(delim)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter to use for the [[String_List|String List]]. If the value is {{code|json}} then a [[JSON_Array|JSON Array]] is returned.}}

   |examples=
   To get the names of all of the maps in a [[String_List|String List]].
   <source lang="mtmacro" line>
   [h: maps = getAllMapNames()]
   </source>

   To get the names of all of the maps in a [[JSON_Array|JSON Array]]
   <source lang="mtmacro" line>
   [h: maps = getAllMapNames("json")]
   </source>
   |also=
   {{func|getCurrentMapName}} {{func|getVisibleMapNames}}

   }}

`Category:Map Function <Category:Map_Function>`__
