.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenOpacity
   |version=1.4.2.0
   |description=sets the opacity value of the corresponding token.  

   |usage=
   <source lang="mtmacro">
   setTokenOpacity(value)
   setTokenOpacity(value, id)
   setTokenOpacity(value, id, mapname)
   </source>

   '''Parameters'''
   {{param|value|The value of the opacity to set, ranging from 0 (completely transparent) to 100 (completely opaque).}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to retrieve the opacity, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [h: setTokenOpacity(50, "Dragon")]
   [h, token("Dragon"): setTokenOpacity(75)]</source>
   |changes={{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:VBL Function <Category:VBL_Function>`__
