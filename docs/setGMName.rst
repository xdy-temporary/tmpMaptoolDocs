.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setGMName
   |trusted=true
   |version=1.3b49
   |description=
   Sets the GM Name of a token. 

   |usage=
   <source lang="mtmacro" line>
   setGMName(name)
   </source>
   <source lang="mtmacro" line>
   setGMName(name, id)
   </source>
   '''Parameters'''
   {{param|name|A string that is set as the GM Name on the token.}}
   {{param|id|The token id of the token that has its GM Name set. Defaults to the [[Current_Token|Current Token]].}}

   |examples=
   Sets the GM Name of the [[Current_Token|Current Token]] to {{code|New GM Name}}.
   <source lang="mtmacro" line>
   [h: setGMName("New GM Name")]
   </source>

   Sets the GM Name of all selected tokens to {{code|New GM Name}}.
   <source lang="mtmacro" line>
   [h: SelectedTokens = getSelected()]
   [h,foreach(TokenID, SelectedTokens), code:
   {
   [h: setGMName("New GM Name", TokenID)]
   }]
   </source>

   |also=
   {{func|getGMName}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
