.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using current functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getState
   |version=1.3b40
   |description=
   Checks whether the specified [[State|State]] is active on a token, returning {{true}} or {{false}}.

   |usage=
   <source lang="mtmacro">
   getState(state)
   getState(state, id)
   getState(state, id, mapname)
   </source>
   '''Parameters'''
   {{param|state|The name of the state to check for.}}
   {{param|id|The token {{code|id}} of the token to check for the state.  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [if(getState("Dead"), "You are dead!", "You are not dead (yet!)")]
   </source>

   |also=
   [[State|State]], [[setState|setState()]], [[setAllStates|setAllStates()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:State Function <Category:State_Function>`__ `Category:Token
Function <Category:Token_Function>`__
