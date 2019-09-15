.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getSightType
   |version=1.3b48
   |description=
   Returns the type of [[Token:sight|sight]] that the [[Current_Token|Current Token]] has.

   |usage=
   <source lang="mtmacro" line>
   getSightType()
   getSightType(id)
   getSightType(mapname)
   </source>

   '''Parameters'''
   {{param|id|The {{code|id}} of the token to have the [[State|State]] set.  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}

   }}

`Category:Sight Function <Category:Sight_Function>`__ `Category:Token
Function <Category:Token_Function>`__
