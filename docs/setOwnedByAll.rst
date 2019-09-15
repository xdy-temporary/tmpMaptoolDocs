.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setOwnedByAll
   |version=1.4.2.0
   |description=
   Allows changing the '''ownedByAll''' value of a token.

   |usage=
   <source lang="mtmacro" line>
   setOwnedByAll(owned)
   setOwnedByAll(owned, id)
   setOwnedByAll(owned, id, mapname)
   </source>
   '''Parameter'''
   {{param|owned|The value of the setting to set, {{true}} or {{false}}.}}
   {{param|id|The token {{code|id}} of the token which has its [[Owned_by_All|Owned by All]] status set, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   <source lang="mtmacro" line>
   [h: setOwnedByAll(1)]
   [h: setOwnedByAll(0, "Dragon")]
   </source>

   |also=
   {{func|getOwners}}, {{func|isOwner}}, {{func|isOwnedByAll}}

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
