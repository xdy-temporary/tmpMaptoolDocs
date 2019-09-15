.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getOwnedNames
   |trusted=true
   |version=1.3b48
   |description=Returns a list containing the names of the [[Token|token]]s on the current [[Map|map]] that are owned by the specified player. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[String_List|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|json array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage=
   <source lang="mtmacro" line>
   getOwnedNames(player)
   getOwnedNames(player, delim)
   </source>
   {{code|delim}} is the delimiter used to separate the values in the [[String_List|string list]] which defaults to {{code|","}} if not specified.

   |examples=
   To display the ids of all of the [[Token|token]]s on the current [[Map|map]] by the [[Player|Player]] use.
   <source lang="mtmacro" line>
   [h: names = getOwnedNames(getPlayerName())]
   [foreach(name, names, "<br>"): name]
   </source>

   |changes=
   * '''1.3b49''' - Added {{code|json}} delimiter option.

   |also=
   {{roll|foreach}}
   }}

`Category:Find Function <Category:Find_Function>`__
