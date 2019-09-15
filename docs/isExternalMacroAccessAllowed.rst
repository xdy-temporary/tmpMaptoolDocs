.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= isExternalMacroAccessAllowed
   |version=1.5.0
   |description=
   Returns {{true}} if the client is configured to allow external macro access (see '''Allow External Macro Access''' in MapTool Preferences).  When enabled, this allows the use of other macro functions such as {{func|exportData}}.

   |usage=
   <source lang="mtmacro" line>
   isExternalMacroAccessAllowed()
   </source>

   |examples=
   '''1. Test to see if the current client can access external resources from macros.'''

   <source lang="mtmacro" line>
   This client has external access [r,if(isExternalMacroAccessAllowed()): "Enabled"; "Disabled"]
   </source>

   |changes=
   }}

`Category:Permission Function <Category:Permission_Function>`__
