.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getExposedTokens
   |trusted=true
   |version=1.3b48
   |description=Gets a list containing the ids of all of the [[Token:token|token]]s on the current [[Map:map|map]] that have been exposed, (i.e. not covered by [[Map:fog_of_war|fog of war]]). The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of ',' is used.
   * If the delimiter ''"json"'' then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage=
   <source lang="mtmacro" line>
   getExposedTokenNames()
   getExposedTokenNames(delim)
   </source>

   If delim is specified then it is used as the delimiter that separates the [[Token:token|token]] ids.

   |example=
   The following example will print out the ids of all the [[Token:token|token]]s on the current [[Map:map|map]] not covered by [[Map:fog_of_war|fog of war]].
   <source lang="mtmacro" line>
   [h: ids = getExposedTokens()]
   [r: foreach(id, ids "<br>"): id]
   </source>

   |changes=
   * '''1.3b49''' - Added ''"json"'' delimiter option.
   }}

`Category:Find Function <Category:Find_Function>`__
