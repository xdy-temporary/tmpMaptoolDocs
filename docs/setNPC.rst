.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setNPC
   |trusted=true
   |version=1.3b48
   |description=
   Sets a [[Token|Token]] to a [[NPC_Token|NPC Token]].

   |usage=
   <source lang="mtmacro" line>
   setNPC()
   setNPC(id)
   setNPC(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its NPC status set, defaults to the [[Current_Token|Current Token]].}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |also=
   [[isPC|isPC()]], 
   [[setPC|setPC()]], 
   [[isNPC|isNPC()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
