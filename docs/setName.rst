.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setName
   |version=1.3b40
   |description=
   Sets the name of a [[Token|Token]]. 

   |usage=
   <source lang="mtmacro" line>
   setName(name)
   setName(name, id)
   setName(name, id, mapname)
   </source>
   '''Parameter'''
   {{param|name|The name to set on the current token.}}
   {{param|id|The token {{code|id}} of the token which has its name set. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
