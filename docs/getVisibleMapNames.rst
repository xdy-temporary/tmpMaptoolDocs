.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getVisibleMapNames
   |version=1.3b55
   |description=
   Returns the names of all of the player visible maps as either a [[String_List|String List]] or [[JSON_Array|JSON Array]]. 

   |usage=
   <source lang="mtmacro" line>
   getVisibleMapNames()
   </source>
   <source lang="mtmacro" line>
   getVisibleMapNames(delim)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter to use for the [[String_List|String List]]. If the value is {{code|json}} then a [[JSON_Array|JSON Array]] is returned.}}

   |examples=
   To get the names of all of the player visible maps in a [[String_List|String List]].
   <source lang="mtmacro" line>
   [h: maps = getVisibleMapNames()]
   </source>

   To get the names of all of the player visible maps in a [[JSON_Array|JSON Array]]
   <source lang="mtmacro" line>
   [h: maps = getVisibleMapNames("json")]
   </source>
   |also=
   {{func|getCurrentMapName}} {{func|getAllMapNames}}

   }}

`Category:Map Function <Category:Map_Function>`__
