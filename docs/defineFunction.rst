.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Could use examples of the ignoreOutput and newScope parameters.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=defineFunction
   |trusted=true
   |version=1.3b51
   |description=
   Defines a user function that can be used anywhere that core functions can be used. A user defined function is a link to another macro. A special macro labeled [[onCampaignLoad|onCampaignLoad]] is useful for defining functions upon the loading of your campaign. This because the function will be defined AFTER the macro has been run. In case of [[onCampaignLoad|onCampaignLoad]], that macro is always run when the campaign is loaded. This saves you the hassle of manually requiring to run this macro to enable the definition.

   |usage=
   <source lang="mtmacro" line>
   defineFunction(function, macro)
   </source>
   <source lang="mtmacro" line>
   defineFunction(function, macro, ignoreOutput)
   </source>
   <source lang="mtmacro" line>
   defineFunction(function, macro, ignoreOutput, newScope)
   </source>
   '''Parameters'''
   {{param|function|The name of the user defined function to be defined. }}
   {{param|macro|The name and location of the macro that is called when the user defined function is used.}}
   {{param|ignoreOutput|If the defined function should ignore all output and only return the value of {{code|macro.return}}, defaults to {{false}}.}}
   {{param|newScope|If the defined function should create a new variable scope when executed, defaults to {{true}}. A new variable scope means that the defined function can only read the variables of the macro that called it; if you do not create a new scope the defined function can read, update, and create variables in its parent's variable scope. Updating variables in the parent's scope includes over-writing any parameters that a parent might have stored within {{func|arg}}, if a user-defined function that does not create a new scope is called within another user-defined function.}}

   |example=
   <source lang="mtmacro" line>
   [h: defineFunction("character.heal", "heal@Lib:Character")]
   </source>

   Defines a function {{code|character.heal()}} which calls {{code|heal@Lib:Character}} when evoked. Note that in this case there must exist a function called "heal" on a token called "lib:Character". The advantage of using the prefix "lib:" on the token name is that it becomes a "lib:token" which is accessible from ANY map instead of only the map you happen to have active. 

   Should you pass on any arguments e.g.
   <source lang="mtmacro" line>
   [h: character.heal("hello", "hi")]
   </source>
   then these parameters can be accessed inside {{code|character.heal()}} by using
   <source lang="mtmacro" line>
   [h: firstArg = arg(0)]
   [h: theOtherOne = arg(1)]
   </source>

   |also=
   {{func|oldFunction}}, 
   {{func|arg}}, 
   {{func|argCount}}, 
   [[onCampaignLoad|onCampaignLoad]]

   |changes=
   {{change|1.3b56|Added {{code|ignoreOutput}} and {{code|newScope}} parameter options.}}
   }}

`Category:User Defined Function <Category:User_Defined_Function>`__
