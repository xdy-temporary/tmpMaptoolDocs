.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setSightType
   |version=1.3b48
   |description=
   Sets the type of [[Token:sight|sight]] that the [[Current_Token|Current Token]] has.

   |usage=
   <source lang="mtmacro" line>
   setSightType(type)
   setSightType(type, id)
   setSightType(type, id, mapname)
   </source>

   '''Parameters'''
   {{param|type|The type of sight to set.}}
   {{param|id|The {{code|id}} of the token to set the [[Token:sight|sight]].  Defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}

   }}

`Category:Sight Function <Category:Sight_Function>`__
