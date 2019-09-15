.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using the new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=createMacro
   |version=1.3b48
   |description=
   Creates a [[Macro_Button|macro button]] for the [[Current_Token|Current Token]] and returns the index of the newly created button.

   |usage=
   <source lang="mtmacro" line>
   createMacro(label, command)
   </source>
   <source lang="mtmacro" line>
   createMacro(label, command, props)
   </source>
   <source lang="mtmacro" line>
   createMacro(label, command, props, delim)
   </source>
   <source lang="mtmacro" line>
   createMacro(label, command, props, delim, id)
   </source>
   '''JSON-only syntax'''
   <source lang="mtmacro" line>
   createMacro(props)
   </source>
   <source lang="mtmacro" line>
   createMacro(props, id)
   </source>
   '''Parameters'''
   {{param|label|The label for the macro button.}}
   {{param|command|The command to run when the macro button is clicked, or the macro is called.}}
   {{param|props|A [[String_Property_List|String Property List]] or [[JSON_Object|JSON Object]] containing the properties for the button.
   ** {{code|applyToSelected}} - Should the macro be applied to the selected tokens.
   ** {{code|autoExecute}} - If the macro will be automatically executed when the button is clicked, accepts {{true}} or {{false}}.
   ** {{code|color}} - The name of the color for the button.
   ** {{code|command}} - The command for the macro (only when using JSON version of function).
   ** {{code|fontColor}} - The name of the font color for the button.
   ** {{code|fontSize}} - The size of the font for the button.
   ** {{code|includeLabel}} - If the label will be output when the button is clicked. Accepts {{true}} or {{false}}.
   ** {{code|group}} - The name of the group that the button belongs to.
   ** {{code|sortBy}} - The sort by value of the macro button.
   ** {{code|label}} - The label for the button.
   ** {{code|maxWidth}} - The maximum width of the button.
   ** {{code|minWidth}} - The minimum width of the button.
   ** {{code|playerEditable}} - Is the button player editable, accepts {{true}} or {{false}}.
   ** {{code|tooltip}} - The tool tip for the macro button.
   ** {{code|compare}} - Takes a [[JSON_Array|JSON Array]] which can contain one or more of the following keywords (only usable with JSON version of the function).
   *** {{code|applyToSelected}} - Use the macro applyToSelected for common macro comparisons.
   *** {{code|autoExecute}} - Use the macro autoExec for common macro comparisons.
   *** {{code|command}} - Use the macro command for common macro comparisons.
   *** {{code|group}} - Use the macro group for common macro comparisons.
   *** {{code|includeLabel}} - Use the macro includeLabel for common macro comparisons.
   *** {{code|sortPrefix}} - Use the macro sortPrefix for common macro comparisons.  }}
   {{param|delim|The delimiter used in the [[String_Property_List|String Property List]] that is sent to the {{code|props}} parameter, defaults to {{code|";"}}. If you are sending a [[JSON_Object|JSON Object]] to the {{code|props}} parameter, and using the {{code|id}} parameter, you can set this to {{code|"json"}}.}}
   {{param|id|The token {{code|id}} of the token that the macro is created on. {{TrustedParameter}} }}

   ''Note: It appears that if a JSON object is passed as {{code|props}} that contains a key of {{code|index}} and that macro index already exists in the destination token, the existing macro will be overwritten.  A workaround is to remove that key from the JSON object prior to calling this function.''

   |example=
   <source lang="mtmacro" line>
   [createMacro("Test", "this is a test", "autoExecute=true;color=blue", ";") ]
   [createMacro("Another Test", "this is a test", 
                "autoExecute=true;color=red;fontColor=white", ";") ]
   </source>
   Will create the following buttons on the current token.
   [[Image:createMacros.png|Image:createMacros.png]]

   Note that if you want to provide a macro command in the command section, you will have issues with quotations as you cannot use double quotes " inside, so macro commands need to be with single ' quotes. 
   <source lang="mtmacro" line>
   [h: createMacro("myMacro", "[macro('aMacro@Lib:Test'): 'aParameter']",
       "autoExecute=true;group=Weapons") ]
   </source>
   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added {{code|id}} parameter option, and JSON-only parameter syntax.}}
   {{change|1.3b53|Added ability for {{code|command}}, {{code|compare}}, {{code|playerEditable}}, {{code|applyToSelected}}, {{code|autoExec}}, {{code|group}}, and {{code|tooltip}} parameters.}}
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
