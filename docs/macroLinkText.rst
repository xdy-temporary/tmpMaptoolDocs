.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=macroLinkText
   |version=1.3b48
   |description=
   Creates the text that would appear in a HTML tag for a link which will run the specified macro when clicked on. This is useful for callbacks in {{roll|dialog}} or {{roll|frame}}. If you just want to send a click-able link to someone use {{func|macroLink}}.

   |usage=
   <source lang="mtmacro" line>
   macroLinkText(macroName)
   </source>
   <source lang="mtmacro" line>
   macroLinkText(macroName, output)
   </source>
   <source lang="mtmacro" line>
   macroLinkText(macroName, output, args)
   </source>
   <source lang="mtmacro" line>
   macroLinkText(macroName, output, args, target)
   </source>
   '''Parameters'''
   {{param|macroName|The name of the macro to run when the link is clicked.  The {{code|macroName}} is in the standard macro reference format (e.g. {{code|Macro@Lib:Token}})}}
   {{param|output|Who the output of the macro should go to, values are (defaults to {{code|none}}):}}
   ** {{code|self}} - Display only to person who clicked on the link.
   ** {{code|gm}} - Display to GM.
   ** {{code|all}} - Everyone (acts like a {{code|/say}})
   ** {{code|none}} - Discard any output.
   ** {{code|gm-self}} - Display to GM and the person executing the link.
   ** {{code|list}} - Displays to a list of players. When the {{code|output}} parameter is {{code|"list"}} then the macro link expects the {{code|args}} parameter to be a [[JSON_Object|JSON Object]], that contains a field called {{code|mlOutputList}} which is a [[JSON_Array|JSON Array]] containing the players to send the output to.
   {{param|args|Any arguments to be passed to the macro when it is called.}}
   {{param|target|Which tokens to run the macro on. Target can be one or more of the following separated by commas (defaults to {{code|impersonated}}):}}
   ** {{code|impersonated}} - The impersonated [[Token|Token]].
   ** {{code|selected}} - The selected [[Token|Token]]/s.
   ** [[Token_ID|Token ID]] - The {{code|id}} of a [[Token|Token]].

   |examples=
   To create the text that would go inside a form element as the {{code|action}} attribute, and that will call a macro named {{code|Test}} on the [[Library_Token|Library Token]] named {{code|Lib:Test}}:
   <source lang="mtmacro" line>
   [r: macroLinkText("Test@Lib:Test","", "gm")]
   </source>
   Returns: {{code|macro://Test@Lib:Test/gm/impersonated?}}

   To create the text that would go inside a form element as the {{code|action}} attribute and call the {{code|AddWeapon}} on the [[Library_Token|Library Token]] named {{code|Lib:PC}} which will act upon the [[Current_Token|Current Token]]:
   <source lang="mtmacro" line>
   [r:macroLinkText('AddWeapon@Lib:PC', 'none', '', currentToken())]
   </source>
   Returns: {{code|macro://AddWeapon@Lib:PC/none/#ID#?}} where {{code|#ID#}} is the {{code|id}} of the [[Current_Token|Current Token]].

   Sending to multiple players and the GM in 1.3b55
   <source lang="mtmacro" line>
   [h: outputTo = '["Fred", "Barney", "gm"]']
   [h: args = json.set("{}", "mlOutputList", outputTo)]
   [r: macroLinkText("Click on me!", "Test@Lib:Test", "list", args)]
   </source>

   Correctly modifying the colour of the link, works both in the chat box and in forms:
   <source lang="mtmacro" line>
   [r: strformat('<a style="color:red" href="%s">Click Me</a>', macroLinkText("Click Me Macro@Lib:Test"))] 
   </source>

   |also=
   {{func|macroLink}}

   |changes=
   {{change|1.3b55|Added {{code|gm-self}} and {{code|list}} output options.}}
   {{change|1.3b56|Links created using this function will no longer show a tooltip when displayed in a dialog or frame.}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
