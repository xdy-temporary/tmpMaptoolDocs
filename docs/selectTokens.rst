.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=selectTokens
   |version=1.3b68
   |description=
   Selects one or more visible tokens on the map. 

   |usage=
   <source lang="mtmacro" line>
   selectTokens()
   </source>
   <source lang="mtmacro" line>
   selectTokens(id, add)
   </source>
   <source lang="mtmacro" line>
   selectTokens(tokens, add, delim)
   </source>

   '''Parameter'''
   * {{code|id}} - the id string or token name of a specific token to select (the examples below use token ''names'', but IDs are also permitted); if left blank ''all'' visible tokens are selected.
   * {{code|add}} - if the value of add is {{code|true(1)}}, the selections will be added to the current set of selected tokens; if the value is {{code|false(0)}} currently selected tokens will be deselected before new tokens are selected. Defaults to false. 
   * {{code|tokens}} - a [[String_List|String List]] of tokens to select.
   * {{code|delim}} - Specifies the delimiter used in the string list that is supplied. If the delimiter is "json", then the value for {{code|tokens}} may be a [[JSON_Array|JSON Array]] instead. '''Note: if using a JSON Array or String List, both {{code|add}} and {{code|delim}} must be specified.'''

   |example=
   To select a single token with the name "Adventurer":
   <source lang="mtmacro" line>
   [h:selectTokens("Adventurer")]
   </source>

   To select a list of [[Token|Token]]s using a [[String_List|String List]], replacing the current selection
   <source lang="mtmacro" line>
   [h:selectTokens("Adventurer, Orc 2, Goblin 1", 0, ",")]
   </source>

   To select a list of [[Token|Token]]s using a [[JSON_Array|JSON Array]], adding the specified tokens to the current set of selected [[Token|Token]]s:
   <source lang="mtmacro" line>
   [h:selectTokens("['Adventurer', 'Orc 2', 'Goblin 1']", 1, "json")]
   </source>

   |also=
   [[deselectTokens|deselectTokens()]],
   [[getSelected|getSelected()]],
   [[getSelectedNames|getSelectedNames()]]

   |changes=
   * '''1.3b68''' - Function added.

   }}

`Category:Token Function <Category:Token_Function>`__
