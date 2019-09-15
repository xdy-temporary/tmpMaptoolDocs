.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setGMNotes
   |trusted=true
   |version=1.3b48
   |description=
   Sets the [[GM|GM]] notes of the [[Current_Token|Current Token]]. 

   |usage=
   <source lang="mtmacro" line>
   setGMNotes(notes)
   setGMNotes(notes, id)
   setGMNotes(notes, id, mapname)
   </source>

   '''Parameter'''
   {{param|notes|The GM notes to set on the token.
   {{param|id|The token {{code|id}} of the token to set the GM notes on. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}


   }}

`Category:Token Function <Category:Token_Function>`__
