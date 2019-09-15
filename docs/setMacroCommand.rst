.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setMacroCommand
   |trusted=true
   |version=1.3b48
   |description=
   Sets the command that will be run when the [[Token:Macro_Button|Macro Button]] is pressed.  Note because of the way the parser interprets values within [] you may have to use the [[Macros:Functions:encode|encode()]] and [[Macros:Functions:decode|decode()]] functions with the string.

   |usage=
   <source lang="mtmacro" line>
   setMacroCommand(index, command)
   </source>
   <source lang="mtmacro" line>
   setMacroCommand(index, command, id)
   </source>
   '''Parameters'''
   {{param|index|The index of the macro button.}}
   {{param|command|A string containing the command to set on the macro button.}}
   {{param|id|The token {{code|id}} of the token that the command is set on.}}

   |examples=
   <source lang="mtmacro" line>
   [h: setMacroCommand(1, "[macro('Test@Lib:Test'): '']")]
   </source>

   |changes=
   {{change|1.3b49|Changed to a trusted function.}}
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
