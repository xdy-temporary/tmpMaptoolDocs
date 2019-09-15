.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenOpacity
   |version=1.4.2.0
   |description=
   Returns the opacity value of the corresponding token.  

   |usage=
   <source lang="mtmacro">
   setTokenOpacity()
   setTokenOpacity(id)
   setTokenOpacity(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to retrieve the opacity, defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   The opacity for the Dragon token is: [r: getTokenOpacity("Dragon")]
   [h, token("Dragon"): opacity = getTokenOpacity()]
   </source>
   |changes={{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:VBL Function <Category:VBL_Function>`__
