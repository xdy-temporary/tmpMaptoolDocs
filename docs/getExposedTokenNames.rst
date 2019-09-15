.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getExposedTokenNames
   |trusted=true
   |version=1.3b48
   |description=Gets a list containing the names of all of the [[Token:token|token]]s on the current [[Map:map|map]] that have been exposed, (i.e. not covered by [[Map:fog_of_war|fog of war]]). The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned and the default value of {{code|","}} is used.
   * If the delimiter {{code|"json"}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise, a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    
   |usage=
   <source lang="mtmacro" line>
   getExposedTokenNames()
   getExposedTokenNames(delim)
   </source>

   If delim is specified then it is used as the delimiter that separates the [[Token:token|token]] names.

   |example=
   The following example will print out the names of all the [[Token:token|token]]s on the current [[Map:map|map]] not covered by [[Map:fog_of_war|fog of war]].
   <source lang="mtmacro" line>
   [h: names = getExposedTokenNames()]
   [r: foreach(name, names, "<br>"): name]
   </source>

   The following example will return the exposed tokens from the TOKEN layer only.
   <source lang="mtmacro" line>
   <!-- get all tokens from the token layer and store in json array -->
   [h:allToks      = getTokenNames("json",'{layer:["TOKEN"]}')]
   <!-- get all exposed tokens from map -->
   [h:allExposed   = getExposedTokenNames("json")]
   <!-- get the intersection of token layer tokens and all the exposed tokens, resulting in token layer exposed tokens only -->
   [h:tokExposed   = json.intersection(allToks, allExp)]
   <!-- sort the result ascending -->
   [h:tokExposed   = json.sort(allToks, allExp,"a")]
   </source>

   This is exactly the same example as the one above, but then nested, so you can have the result in one line of code.
   <source lang="mtmacro" line>
   [h:tokExposed   = json.sort(json.intersection(getTokenNames("json",'{layer:["TOKEN"]}'), getExposedTokenNames("json")),"a")]
   </source>


   |changes=
   * '''1.3b49''' - Added ''"json"'' delimiter option.
   * '''1.3b91''' - Apparently now tokens from ALL layers are returned, instead of TOKEN LAYER only. Added example to correct this.

   }}

`Category:Find Function <Category:Find_Function>`__ `Category:Token
Function <Category:Token_Function>`__
