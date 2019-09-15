.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getNotes
   |version=1.3b48
   |description=Returns the [[Notes|token notes]] for the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   getNotes()
   getNotes(id)
   getNotes(id, mapname)
   </source>


   '''Parameter'''
   {{param|id|The token {{code|id}} of the token to get the notes from. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

See also `setNotes <setNotes>`__

`Category:Token Function <Category:Token_Function>`__
