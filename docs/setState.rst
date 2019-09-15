.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setState
   |version=1.3b40
   |description=
   Sets the value of the [[State|State]] on [[Token|Token]]. If The value is {{false}} then the [[State|State]] is unset if it is non-zero({{true}}) then it is set.

   |usage=
   <source lang="mtmacro" line>
   setState(state, value)
   setState(state, value, id)
   setState(state, value, id, mapname)
   </source>
   '''Parameters'''
   {{param|state|The name of the state to set on the token.}}
   {{param|value|The value of the state to set, {{code|true}}({{code|1}}) or {{code|false}}({{code|0}}).}}
   {{param|id|The {{code|id}} of the token to have the [[State|State]] set.  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   To set the "Dead" [[Token:state|Token State]] on the [[Current_Token|Current Token]]
   <source lang="mtmacro" line>
   [h: setState("Dead", 1)]
   </source>

   To reset the "Dead" [[Token:state|Token State]] on the [[Current_Token|Current Token]]
   <source lang="mtmacro" line>
   [h: setState("Dead", 0)]
   </source>

   |also=
   [[State|State]],
   [[getState|getState()]],
   [[setAllStates|setAllStates()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:State Function <Category:State_Function>`__ `Category:Token
Function <Category:Token_Function>`__
