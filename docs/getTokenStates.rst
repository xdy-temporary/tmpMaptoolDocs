.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenStates
   |version=1.3b51
   |description=
   Returns the valid states in the campaign settings in either a [[String_List|String List]] or [[JSON_Array|JSON Array]]. 

   |usage=
   <source lang="mtmacro" line>
   getTokenStates()
   </source>
   <source lang="mtmacro" line>
   getTokenStates(delim)
   </source>
   <source lang="mtmacro" line>
   getTokenStates(delim, groupName)
   </source>
   '''Parameter'''
   * {{code|delim}} - Specifies the delimiter used in the string list that is returned, defaultis {{code|","}}. If the value is set to {{code|json}}, the function returns a JSON array instead.
   * {{code|groupName}} - Specifies the name of the group to get the states for. '''Note that if you wish to use the {{code|groupname}} parameter, you MUST set a delimiter.

   |example=
   To get a [[String_List|String List]] of the valid [[Token_State|Token State]]s in the campaign.
   <source lang="mtmacro" line>
   [h: states = getTokenStates()]
   </source>

   To get a [[JSON_Array|JSON Array]] of the valid [[Token_State|Token State]]s in the campaign.
   <source lang="mtmacro" line>
   [h: states = getTokenStates("json")]
   </source>

   To get a [[JSON_Array|JSON Array]] of the valid [[Token_State|Token State]]s in the ''Damage'' group in the campaign in 1.3b55 or later.
   <source lang="mtmacro" line>
   [h: states = getTokenStates("json", "Damage")]
   </source>



   |changes=
   * '''1.3b55''' - Added the {{code|groupName}} parameter.

   }}

`Category:State Function <Category:State_Function>`__
