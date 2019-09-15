.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getName
   |version=1.3b40
   |description=
   Returns the name of a [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   getName()
   getName(id)
   getName(id, mapname)
   </source>
   '''Parameters'''
   {{param|id|The token {{code|id}} of the token to name, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [TokenList = getTokens("json")]
   [foreach(Token, TokenList, "<br>", "json"): getName(Token) + "'s ID is " + Token]
   </source>

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
