.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=isOwnedByAll
   |version=1.3b48
   |description=
   Returns {{true}} if a [[Token|Token]] has the [[Owned_by_All|Owned by All]] check box checked.

   |usage=
   <source lang="mtmacro" line>
   isOwnedByAll()
   isOwnedByAll(id)
   isOwnedByAll(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its [[Owned_by_All|Owned by All]] status checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   Returns {{code|Anyone can edit me}} if the [[Current_Token|Current Token]] has the [[Owned_by_All|Owned by All]] check box checked.
   <source lang="mtmacro" line>
   [r, if(isOnwedByAll()): "Anyone can edit me"]
   </source>

   |also=
   [[getOwners|getOwners()]], 
   [[isOwner|isOwner()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
