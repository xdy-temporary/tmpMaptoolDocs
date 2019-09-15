.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroName
   |version=1.3b48
   |description=
   Returns the name of the macro being executed via [[macro_(roll_option)|[macro():]]]. If the macro typed into chat, run by clicking on a [[Macro_Button|macro button]], or run via the [[Token:popup_menu|token popup menu]] then this function will return "chat".

   |usage=
   <source lang="mtmacro" line>
   getMacroName()
   </source>
   |examples=
   <source lang="mtmacro" line>
   [h: macroName = getMacroName()]
   [if(macroName == "chat", "You are running from chat", "You are running the macro called " + macroName)]
   </source>
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
