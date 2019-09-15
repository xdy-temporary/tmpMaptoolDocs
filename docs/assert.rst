.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=assert
   |version=1.3b49
   |description=
   Halts execution and prints a custom error message if a condition is {{false}}.  Note that the error message will be displayed in chat even if the command itself is in a {{code|[H: ]}} block.

   |usage=
   <source lang="mtmacro" line>
   assert(condition, message)
   </source>
   <source lang="mtmacro" line>
   assert(condition, message, prefix)
   </source>
   '''Parameters'''
   {{param|condition|The test condition that must evaluate to {{true}} for the macro to continue.}}
   {{param|message|The custom error message that is presented if the macro is halted due to the {{false}} condition.}}
   {{param|prefix|Determines if the error message should have the message prefix {{code|"Macro defined error: "}}. Defaults to {{true}}, set to {{false}} if you do not wish your custom error message to have the message prefix.}}

   |examples=
   Checks to see if a player is a GM, and if they are not halts execution of the macro and displays output.
   <source lang="mtmacro" line>
   [h: assert(isGM(),"This macro is for GM use only.",0)]
   </source>
   Chat output (if player is not GM): {{code|This macro is for GM use only.}}


   Halts execution of the macro if {{code|var}} is a number.  This is useful for making sure the variables you work with are the variable type you expect.
   <source lang="mtmacro" line>
   [h: assert(! isNumber(var), "The variable is a number.",1)]
   </source>
   Chat output (if {{code|var}} is a number): {{code|Macro defined error: The variable is a number.}}

   Bear in mind, {{code|isNumber(var)}} returns {{true}} when var is a number, but assert continues when condition is {{true}}.  Using {{code|! isNumber(var)}} inverts the boolean value.

   ===Usage Notes===
   When aborting a macro called from another macro (for example, a library token), all macros are aborted, not just the one executing. 
   Since 1.5.0 you can change that behaviour by using macro.catchAssert. 

   |also=
   {{ func|isGM}}

{{ func|isNumber}} {{ func|abort}}
`macro.catchAssert <macro.catchAssert>`__

\|changes=

}}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
