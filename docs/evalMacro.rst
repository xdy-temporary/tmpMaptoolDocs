.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=evalMacro
   |trusted=true
   |version=1.3b49
   |description=
   Evaluates and "executes" the macro in a string and returns the result. The string contains the same type of macro commands that you would put in a token macro with the exception that it can not contain slash commands.

   If you are performing rolls in the macro that create tool tips or use {{code|[e: ]}} then you will have to use either {{code|{ <nowiki>}</nowiki>}} or {{code|[r: ]}} to display the output otherwise you will get incorrect formatting. 

   The {{func|evalMacro}} function executes the macro in the same variable scope (i.e. the executed macro can read and alter variables from the current macro), where as {{func|execMacro}} creates a new variable scope (i.e. the executed macro can neither read nor alter varaibles from the current macro).

   The advantage of this function over {{func|eval}} is that with {{func|eval}} you can only give a string as parameter that can be evaluated (e.g. {{code|"3+5"}}), while with {{func|evalMacro}} you can give anything as parameter but only the parts between {{code|[}}brackets{{code|]}} will be evaluated. (e.g. {{code|"Your resulting roll is [r:1d10]"}})

   |usage=
   <source lang="mtmacro" line>
   evalMacro(macroString)
   </source>
   <source lang="mtmacro" line>
   execMacro(macroString)
   </source>
   '''Parameter'''
   {{param|macroString|The string containing the macro script that is evaluated/executed.}}

   |examples=
   <source lang="mtmacro" line>
   [h: setNotes(evalMacro('[r,macro("CreateNotes@Lib:Notes"): ""]'))]
   </source>
   Sets the Notes of a [[Token|Token]] to the output of the {{code|CreateNotes}} macro located on the {{code|Lib:Notes}} [[Library_Token|Library Token]].


   <source lang="mtmacro" line>
   [r: evalMacro("[h: TestVar1 = 5][h: TestVar2 = 10][TestVar1+TestVar2]")]
   </source>
   Returns {{code|15}}


   <source lang="mtmacro" line>
   [h: TestVar3 = 10]
   [h: TestVar4 = 20]
   [r: evalMacro("[TestVar3+TestVar4]")]
   </source>
   Returns {{code|30}}


   <source lang="mtmacro" line>
   [h: TestVar3 = 15]
   [h: TestVar4 = 30]
   [h: evalMacro("[TestVar5 = TestVar3+TestVar4]")]
   [TestVar5]
   </source>
   Returns {{code|45}}


   <source lang="mtmacro" line>
   [h: TestVar6 = 20]
   [h: TestVar7 = 40]
   [r: execMacro("[TestVar6+TestVar7]")]
   </source>
   Prompts for the values of {{code|TestVar6}} and {{code|TestVar7}}, then it returns the sum of those two values.


   <source lang="mtmacro" line>
   [h: TestVar8 = 50]
   [h: TestVar9 = 100]
   [h: TestVar10 = 0]
   [h: execMacro("[TestVar10 = TestVar8+TestVar9]")]
   [TestVar10]
   </source>
   Returns {{code|0}}


   <source lang="mtmacro" line>
   [r: evalMacro("[h:roll=1d20]You roll [r:roll] and you [r:if(roll<10, 'hit', 'miss')] your target.")]
   </source>
   Returns {{code|You roll 3 and you hit your target.}}


   |also=
   {{func|eval}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
