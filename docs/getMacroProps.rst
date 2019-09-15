.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroProps
   |version=1.3b48
   |description=
   Returns a property list of the properties for a [[Macro_Button|macro button]] for the [[Current_Token|Current Token]]. You can retrieve the index of a [[Macro_Button|macro button]] with the [[getMacroIndexes|getMacroIndexes()]] function.The type of the value returned depends on the delimiter parameter. 

   |usage=
   <source lang="mtmacro" line>
   getMacroProps(index)
   </source>
   <source lang="mtmacro" line>
   getMacroProps(index, delim)
   </source>
   <source lang="mtmacro" line>
   getMacroProps(index, delim, id)
   </source>
   '''Parameters'''
   {{param|index|The index of the [[Macro_Button|macro button]].}}
   {{param|delim|The delimiter used to separate the values in the  [[Macros:string_property_list|string property list]] which defaults to {{code|";"}} if not specified. This function returns a [[JSON_Object|JSON Object]] if {{code|"json"}} is specified.}}
   {{param|id|The token {{code|id}} of the token that the function is executed on. {{TrustedParameter}} }}

   '''Valid Properties for Macro Buttons'''
   * {{code|applyToSelected}} - Should the macro be applied to the selected tokens.
   * {{code|autoExecute}} - If the macro will be automatically executed when the button is clicked, accepts {{true}} or {{false}}.
   * {{code|color}} - The name of the color for the button.
   * {{code|command}} - The command for the macro (only when using JSON version of function).
   * {{code|fontColor}} - The name of the font color for the button.
   * {{code|fontSize}} - The size of the font for the button.
   * {{code|includeLabel}} - If the label will be output when the button is clicked. Accepts {{true}} or {{false}}.
   * {{code|group}} - The name of the group that the button belongs to.
   * index - The index of the button.
   * {{code|sortBy}} - The sort by value of the macro button.
   * {{code|label}} - The label for the button.
   * {{code|maxWidth}} - The maximum width of the button.
   * {{code|minWidth}} - The minimum width of the button.
   * {{code|playerEditable}} - Is the button player editable, accepts {{true}} or {{false}}.
   * {{code|tooltip}} - The tool tip for the macro button.
   * {{code|compare}} - Takes a [[JSON_Array|JSON Array]] which can contain one or more of the following keywords (only usable with JSON version of the function).
   ** {{code|applyToSelected}} - Use the macro applyToSelected for common macro comparisons.
   ** {{code|autoExecute}} - Use the macro autoExec for common macro comparisons.
   ** {{code|command}} - Use the macro command for common macro comparisons.
   ** {{code|group}} - Use the macro group for common macro comparisons.
   ** {{code|includeLabel}} - Use the macro includeLabel for common macro comparisons.
   ** {{code|sortPrefix}} - Use the macro sortPrefix for common macro comparisons.

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added optional token {{code|id}} parameter.}}
   {{change|1.3b53|Added ability for {{code|command}}, {{code|compare}}, {{code|playerEditable}}, {{code|applyToSelected}}, {{code|autoExecute}}, {{code|group}}, and {{code|tooltip}} parameters.}}
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
