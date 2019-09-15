.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroGroup
   |trusted=true
   |version=1.3b51
   |description=
   Gets the indexes of the macro buttons for the specified group.

   |usage=
   <source lang="mtmacro" line>
   getMacroGroup(group)
   </source>
   <source lang="mtmacro" line>
   getMacroGroup(group, delim)
   </source>
   <source lang="mtmacro" line>
   getMacroGroup(group, delim, id)
   </source>
   '''Parameters'''
   * {{code|group}} - The name of the macro group to get the macro button indexes from.
   * {{code|delim}} - The delimiter used in the string list returned, defaults to {{code|","}}. If set to {{code|json}}, then a JSON array is returned.
   * {{code|id}} - The id of the token that the macro group is located on, defaults to the current token. If the id is not specified, this function does not require a Trusted Macro.

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
