.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getOwners
   |version=1.3b48
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] containing the names of the owners of a [[Token|Token]]. The type of the value returned depends on the delimiter parameter. 

   |usage=
   <source lang="mtmacro" line>
   getOwners()
   getOwners(delim)
   getOwners(delim, id)
   getOwners(delim, id, mapname)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the [[String_List|String List]], defaults to {{code|","}}. If set to {{code|"json"}}, this function will return a [[JSON_Array|JSON Array]] instead of a [[String_List|String List]].}}
   {{param|id|The token {{code|id}} of the token which has its owners returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   To display the [[Owners|owners]] of the [[Current_Token|Current Token]] use.
   <source lang="mtmacro" line>
   [h: names = getOwners()]
   [foreach(name, names, "<br>"): name]
   </source>

   |also=
   [[isOwnedByAll|isOwnedByAll()]], 
   [[isOwner|isOwner()]]

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
