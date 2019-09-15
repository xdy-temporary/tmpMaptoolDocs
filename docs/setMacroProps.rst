.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using the new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setMacroProps
   |version=1.3b48
   |description=
   Sets the properties for the specified [[Token:Macro_Button|Macro Button]] on the [[Current_Token|Current Token]] . The properties are passed to this function as a [[String_Property_List|String Property List]]. This function accepts either a [[Token:Macro_Button_Index|Macro Button Index]] or the label of a [[Token:Macro_Button|Macro Button]]. If it is a label then all of [[Token:Macro_Button|Macro Button]]s on the [[Current_Token|Current Token]] with a matching label are changed.

   |usage=
   <source lang="mtmacro" line>
   setMacroProps(index, props)
   </source>
   <source lang="mtmacro" line>
   setMacroProps(index, props, delim)
   </source>
   <source lang="mtmacro" line>
   setMacroProps(index, props, delim, id)
   </source>
   <source lang="mtmacro" line>
   setMacroProps(label, props)
   </source>
   <source lang="mtmacro" line>
   setMacroProps(label, props, delim)
   </source>
   <source lang="mtmacro" line>
   setMacroProps(label, props, delim, id)
   </source>
   '''Parameters'''
   {{param|index|The index of the macro button.}}
   {{param|label|The label of the macro button.}}
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
   *** {{code|sortPrefix}} - Use the macro sortPrefix for common macro comparisons.}}
   {{param|delim|The delimiter used in the [[String_Property_List|String Property List]] that is sent to the {{code|props}} parameter, defaults to {{code|";"}} and can be omitted if you are sending a [[JSON_Object|JSON Object]] to the {{code|props}} parameter. If you are sending a [[JSON_Object|JSON Object]] to the {{code|props}} parameter, and using the {{code|id}} parameter, you can set this to {{code|"json"}}.}}
   {{param|id|The token {{code|id}} of the token that the macro button is located on. {{TrustedParameter}} }}

   |example=
   <source lang="mtmacro" line>
   [h: setMacroProps(1, "color=red;fontColor=white")]
   [h: setMacroProps("Attack", "color=red;fontColor=white")]
   </source>

   |changes=
   {{change|1.3b49|Added ability for {{code|props}} to accept a JSON object.}}
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.3b53|Added ability for {{code|command}}, {{code|compare}}, {{code|playerEditable}}, {{code|applyToSelected}}, {{code|autoExecute}}, {{code|group}}, and {{code|tooltip}} parameters.}}

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
