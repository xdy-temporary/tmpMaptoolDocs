.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=isOwner
   |version=1.3b48
   |description=
   Returns {{true}} if the given [[Player|Player]] is an owner of a specific [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   isOwner()
   isOwner(player)
   isOwner(player, id)
   isOwner(player, id, mapname)
   </source>
   '''Parameters'''
   {{param|player|The name of the player to check for ownership, defaults to the [[Current_Player|Current Player]]. }}
   {{param|id|The token {{code|id}} of the token which is checked for ownership, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |examples=
   Returns {{code|You can edit me.}} if the [[Current_Player|Current Player]] is an owner of the [[Current_Token|Current Token]].
   <source lang="mtmacro" line>
   [r, if(isOwner()): "You can edit me."]
   </source>

   Returns {{code|Azhrei can edit me.}} if the given [[Player|Player]] is an owner of the given [[Token|Token]].
   <source lang="mtmacro" line>
   [h: id = getSelected() ]
   [r, if(isOwner("Azhrei", id)): "Azhrei can edit me."]
   </source>

   |also=
   [[getOwners|getOwners()]], 
   [[isOwnedByAll|isOwnedByAll()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
