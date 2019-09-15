.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setHasSight
   |version=1.3b48
   |trusted=false
   |description=
   Enables/disables sight for the [[Current_Token|Current Token]]. If the argument is 0 (false) sight will be disabled on the [[Current_Token|Current Token]]. If it is non-zero (true) sight is enabled.

   |usage=
   <source lang="mtmacro" line>
   setHasSight(state)
   setHasSight(state, id)
   setHasSight(state, id, mapname)
   </source>

   '''Parameters'''
   {{param|state|Boolean - true to enable sight, false to disable }}
   {{param|id|The {{code|id}} of the token to set the sight of.  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   Enables sight for [[Current_Token|Current Token]]
   <source lang="mtmacro" line>
   [h: setHasSight(1)]
   </source>
   Returns: Empty String.

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}


   }}

`Category:Sight Function <Category:Sight_Function>`__
