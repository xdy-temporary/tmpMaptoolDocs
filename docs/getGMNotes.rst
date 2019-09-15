.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getGMNotes
   |trusted=true
   |version=1.3b48
   |description=Returns the [[Token:GM_notes|GM notes]] from the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   getGMNotes()
   getGMNotes(id)
   getGMNotes(id, mapname)
   </source>

   '''Parameter'''
   {{param|id|The token {{code|id}} of the token to get the GM notes from. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

}}

`Category:Token Function <Category:Token_Function>`__
