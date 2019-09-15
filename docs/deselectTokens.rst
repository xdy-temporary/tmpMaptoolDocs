.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=deselectTokens
   |version=1.3b68
   |description=
   Deselects one or more visible tokens on the map. 

   |usage=
   <source lang="mtmacro" line>
   deselectTokens()
   </source>
   <source lang="mtmacro" line>
   deselectTokens(id)
   </source>
   <source lang="mtmacro" line>
   deselectTokens(tokens, delim)
   </source>

   '''Parameter'''
   * {{code|id}} - the id string or name of a specific token to deselect (the examples below use the token name, but token IDs are also valid); if left blank all currently selected tokens are deselected.
   * {{code|tokens}} - a [[String_List|String List]] of tokens to deselect.
   * {{code|delim}} - Specifies the delimiter used in the string list that is supplied. If the delimiter is "json", then the value for {{code|list}} may be a [[JSON_Array|JSON Array]] instead. '''Note: if using a JSON Array or String List, {{code|delim}} must be specified.'''

   |example=
   To deselect a single token with the name "Adventurer":
   <source lang="mtmacro" line>
   [h:deselectTokens("Adventurer")]
   </source>

   To deselect a list of [[Token|Token]]s using a [[String_List|String List]]:
   <source lang="mtmacro" line>
   [h:deselectTokens("Adventurer, Orc 2, Goblin 1", 0, ",")]
   </source>

   |also=
   [[selectTokens|selectTokens()]],
   [[getSelected|getSelected()]],
   [[getSelectedNames|getSelectedNames()]]

   |changes=
   * '''1.3b68''' - Function added.

   }}

`Category:Token Function <Category:Token_Function>`__
