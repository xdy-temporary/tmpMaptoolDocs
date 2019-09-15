.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{RollOption
   |name=macro
   |version=1.3b46
   |description=
   Runs the named macro, returning its output in the form of the [[macro.return|macro.return]] special variable.

   |usage=
   <source lang="mtmacro" line>
   [macro("macro_name@location"): macro_arguments]
   </source>
   '''Parameters'''
   {{param|macro_name|The name of the macro button that is run.}}
   {{param|location|The location of the macro button that is run.}}
   {{param|macro_arguments|Sent to the called macro in the form of the [[macro.args|macro.args]] special variable.}}
   '''Location Requirements'''

   The {{code|location}} can be one of the following:
   * {{code|TOKEN}} - The currently impersonated token (use the word {{code|TOKEN}}, not the token's name).
   * {{code|campaign}}
   * {{code|global}}
   * {{code|Lib:*}} Library Token - A [[Library_Token|Library Token]] in the current campaign.
   * {{code|this}} - If the macro is calling another macro on the same [[Library_Token|Library Token]], {{code|this}} may be used instead of retyping the full [[Library_Token|Library Token]] name.
   '''Notes'''

   When a token macro calls another macro, the macro instructions in the ''called'' macro are executed against the ''calling'' token (in other words, the macro uses properties available on the calling token and applies all results to that token), unless the focus is explicitly changed to another token via either a roll option, or the {{func|switchToken}} function, or the {{func|getLibProperty}} function within the ''called'' macro. This applies even if the [[Current_Token|Current Token]] was explicitly changed prior to using the {{roll|macro}} roll option.

   Also- as of at least 1.3.b50- a variable must be given for {{code|macro_arguments}}, or the ''"Could not execute the command: Undefined function: MACRO"'' error will result.  However, the variable given as {{code|macro_arguments}} doesn't have to be used, and can be set to an empty string ({{code|""}}).

   This roll option may not interact with other roll options the way you expect.  For example:
   <source lang="mtmacro" line>
   [if(Condition),MACRO("getDamage@Lib:combat"): damageRoll]
   </source>

   {{code|getDamage}} gets executed regardless of the value of {{code|Condition}}.  However, if {{code|Condition}} is not true, the arguments to the macro will be empty instead of containing {{code|damageRoll}}.  You probably want:
   <source lang="mtmacro" line>
   [if(Condition): evalMacro('[MACRO("getDamage@Lib:combat"): damageRoll]')]
   </source>

   |example=
   <source lang="mtmacro" line>
   [MACRO("getDamage@Lib:combat"): damageRoll]
   </source>
   Calls the macro {{code|getDamage}} which resides on a [[Library_Token|Library Token]] called {{code|Lib:combat}}, and passes the variable {{code|damageRoll}} as an argument to the called macro. 

   '''Passing multiple arguments to a called macro'''

   Note that only one variable can be passed to the called macro.  To pass multiple values, you must "package" them into a format that can be stored in a single variable to be passed to the called macro, and then unpackaged appropriately to recover local variables used in the called macro.  [[JSON_Object|JSON Object]]s and [[JSON_Array|JSON Array]]s work very well for this purpose (although string lists and StrProps can also serve this purpose, they have more limitations and are less recommended).  For example, multiple values can be stored into a json array, which becomes the argument passed in the macro call:

   '''Using a [[JSON_Array|JSON Array]] to pass multiple values (order matters, names do not)'''
   <source lang="mtmacro" line>
   [ variable1 = "hello" ]
   [ variable2 = "world" ]
   [ passedVars = json.append( "", variable1, variable2 )] <!-- package up variables into a json array to be passed to called macro -->
   [MACRO("calledMacro@this"): passedVars ] <!-- macro call, with values being passed -->
   [ resultVar = macro.return ]  <!-- this is what you get back from the called macro -->
   </source>
   Within the "called macro", the [[macro.args|macro.args]] (macro arguments) must be unpackaged to recover the values stored in the array:
   <source lang="mtmacro" line>
   [ var1 = json.get( macro.args, 0 )]
   [ var2 = json.get( macro.args, 1 )]
   <!-- do stuff with your new variables -->
   [ macro.return = var1 +" "+ var2 ] <!-- this is what you can send back to the calling macro (can also be another JSON Object or array -->
   </source>
   Note that using a [[JSON_Array|JSON Array]] to pass & unpack values, rather than a [[JSON_Object|JSON Object]], has the added advantage that if the called macro is also a [[user_defined_function|user defined function]] (see [[defineFunction|defineFunction]]), the exact same commands given in the example above can be used to separate individual arguments passed in the calling "function", since function arguments are automatically bundled into a [[JSON_Array|JSON Array]] and passed to the [[macro.args|macro.args]] special variable.

   '''Using a [[JSON_Object|JSON Object]] to pass multiple values (names matter, order does not)'''
   <source lang="mtmacro" line>
   [ variable1 = "hello" ]
   [ variable2 = "world" ]
   [ passedVars = json.set( "{}", "variable2", variable2, "variable1", variable1 )] <!-- package up variables into a json array to be passed to called macro.  Note that the order here does not matter, but the labels in quotes are needed to be able to retrieve the correct values in the called macro -->
   [MACRO("calledMacro@this"): passedVars ] <!-- macro call, with values being passed -->
   [ resultVar = macro.return ]  <!-- this is what you get back from the called macro -->
   </source>
   Within the "called macro", the [[macro.args|macro.args]] (macro arguments) must be unpackaged to recover the values stored in the array:
   <source lang="mtmacro" line>
   [ var1 = json.get( macro.args, "variable1" )]<!-- actually the second label / value pair in the object --> 
   [ var2 = json.get( macro.args, "variable2" )]<!-- the order does not matter, but the label must be accurate to retrieve the correct value -->
   <!-- do stuff with your new variables -->
   [ macro.return = var1 +" "+ var2 ] <!-- this is what you can send back to the calling macro (can also be another JSON Object or array -->
   </source>


   |also=
   [[macro.args|macro.args]], 
   [[macro.return|macro.return]],
   [[defineFunction|defineFunction]],
   [[More_Branching_Options|More Branching Options]]
   }}

`Category:Branching Roll Option <Category:Branching_Roll_Option>`__
