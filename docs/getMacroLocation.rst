.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroLocation
   |version=1.3b48
   |description=
   Returns the location of the macro being executed, the return value will be {{code|"chat"}}, {{code|"global"}}, {{code|"campaign"}} or the label of the token the macro resides on (e.g. {{code|"Lib:Utilities"}} or {{code|"Token:Orc"}}.) Standard PC and NPC tokens will have their label prefixed with {{code|Token:}}.

   |usage=
   <source lang="mtmacro" line>
   getMacroLocation()
   </source>

   |example=
   <source lang="mtmacro" line>
   [h: MacroLocation = getMacroLocation()]
   [if(MacroLocation == "chat", "You are running from chat", "You are running from "+MacroLocation]
   </source>

   |changes=
   {{change|1.3b51|Now accurately reports where the macro button resides.}}

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
