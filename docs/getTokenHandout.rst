.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenHandout
   |description=
   Returns the [[Asset_ID|asset id]] of the handout image for the for the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   getTokenHandout()
   getTokenHandout(size)
   getTokenHandout(size, id)
   getTokenHandout(size, id, mapname)
   </source>

   '''Parameters'''
   {{param|size|OPTIONAL: The size the image should be returned as. If a blank string "", no size adjustment is done. Defaults to "".}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to retrieve the token handout image, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |example=
   To display the image for the current [[Token|Token]].
   <source lang="mtmacro" line>
   <img src='[r:getTokenHandout()]'></img>
   </source>
   |changes={{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

`Category:Token Function <Category:Token_Function>`__
