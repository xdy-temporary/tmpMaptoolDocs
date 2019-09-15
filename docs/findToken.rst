.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=findToken
   |trusted=true
   |version=1.3b48
   |description=Finds a [[Token:token|token]] on the current [[Map:map|map]] by the [[Token:token|token]] name, GM name, or ID and returns its id. If the optional ''mapname'' parameter is supplied that map will be searched instead. If the [[Token:token|token]] is not found then an empty string "" is returned.

   |usage=
   <source lang="mtmacro" line>
   findToken(name/ID)
   findToken(name/ID,mapname)
   </source>
   '''Parameters'''
   {{param|name/ID|Either the name of the token or the ID.}}
   {{param|mapname|Optional name of the map to search for the token on.}}

   |example=
   Search for token on current map
   <source lang="mtmacro" line>
   [h: id = findToken("Hero")]
   [if (id == "", "Token not found!", "Token found")]
   </source>
   Search for token on current map and then search the map named ''Stash'' if not found.
   <source lang="mtmacro" line>
   <!-- Prompts for "TokenName" as it isn't already defined -->
   [h: name = TokenName]
   [h: id = findToken(name)]
   [r, if(id == ""), code: {
       Not on current map. Searching Stash.<br>
       <!-- Search on the map named "Stash" -->
       [h: id = findToken(name, "Stash")]
       [r: if(id == "", name + " not found!", name + " found in Stash")]
   };{
       [r: name] found on map [r: getCurrentMapName()].
   }]
   </source>

   }}

`Category:Find Function <Category:Find_Function>`__ `Category:Token
Function <Category:Token_Function>`__
