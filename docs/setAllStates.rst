.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setAllSates
   |version=1.3b40
   |description=
   Sets all of the [[State|States]] of a [[Token|Token]] to on ({{true}}) or off ({{false}}).

   |usage=
   <source lang="mtmacro">
   setAllStates(value)
   setAllStates(value, id)
   setAllStates(value, id, mapname)
   </source>
   '''Parameter'''
   {{param|value|If all states should be set on or off, {{true}} or {{false}}.}}
   {{param|id|The {{code|id}} of the token that should have its [[State|States]] set.  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   Set all [[Token:state|Token States]] on
   <source lang="mtmacro" line>
   [h: setAllStates(1)]
   </source>
   Set all [[Token:state|Token States]] off
   <source lang="mtmacro" line>
   [h: setAllStates(0)]
   </source>

   |also=
   [[State|State]], [[getState|getState()]], [[setState|setState()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:State Function <Category:State_Function>`__
