.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using the new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=isNPC
   |version=1.3b48
   |description=
   Returns {{true}} if a [[Token|Token]] is a NPC or {{false}} if it is not.

   |usage=
   <source lang="mtmacro" line>
   isNPC()
   isNPC(id)
   isNPC(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its NPC status checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [r, if(isNPC()): "Hello I am an NPC"]
   </source>

   |also=
   [[isPC|isPC()]], 
   [[setPC|setPC()]], 
   [[setNPC|setNPC()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
