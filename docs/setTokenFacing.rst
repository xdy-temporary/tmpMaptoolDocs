.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenFacing
   |trusted=true
   |version=1.3b51
   |description=
   Sets the facing angle of a token.

   |usage=
   <source lang="mtmacro" line>
   setTokenFacing(angle)
   setTokenFacing(angle, id)
   setTokenFacing(angle, id, mapname)
   </source>
   '''Parameters'''
   {{param|angle|The angle as which to set the facing.}}
   {{param|id|The id of the token to set the facing of, defaults to the current token. If this parameter is used, this function requires a trusted macro.}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
