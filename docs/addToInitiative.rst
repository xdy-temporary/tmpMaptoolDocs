.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=addToInitiative
   |description=Adds the [[Current_Token|Current Token]] to the [[Initiative:initiative_panel|initiative panel]]. 
   This function will not assign any initiative value to the [[Token:token|token]]s, you can use the [[setInitiative|setInitiative()]] function
   to set the initiative value of tokens.

   |usage=
   <source lang="mtmacro" line>
   [h: addToInitiative()]
   [H: return = addToInitiative( AllowDuplicates, value ) ]
   </source>
   '''Parameters'''
   * {{code|AllowDuplicates}} - If false (default) then will not add the token if it is already in the initiative list.  If true (1) an additional entry will be added to the initiative list (so there could be multiple initiative entries for the same token).
   * {{code|value}} - The initiative value to set.  If included, the initiative will be set even if the token is already on the initiative list and duplicates are not allowed.
   * {{code|return}} - Returns 1 if added to the initiative, 0 if did not.

   |example=
   The following example shows how to add a [[Current_Token|Current Token]] to the [[Initiative:initiative_panel|initiative panel]], set 
   its initiative and then sort the [[Initiative:initiative_panel|initiative panel]]. Normally you would not sort the [[Initiative:initiative_panel|initiative panel]] every time you add a [[Current_Token|Current Token]] but its done here to show you how it is done.

   <source lang="mtmacro" line>
   [h: addToInitiative()]
   [h: setInitiative(1d20)]
   [h: sortInitiative()]
   </source>

   |also=
   [[setInitiative|setInitiative()]] [[addAllPCsToInitiative|addAllPCsToInitiative()]] [[addAllToInitiative|addAllToInitiative()]]

   }}

`Category:Initiative Function <Category:Initiative_Function>`__
