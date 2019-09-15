.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= getTokenRotation
   |proposed=false
   |trusted=false
   |version=1.5.0
   |description=
   Retrieves the angle of rotation for the token from the default position.  Returned value is in degrees.

   For Square, Round or Figure token types, this is the change in the facing indicator from the default of 0 degrees or no change in facing.  Positive is CW and negative is CCW. Values will range from -270 to +85.

   For Top Down tokens, this is the rotation of the token image itself from the default of 0 degrees.

   |usage=
   <source lang="mtmacro" line>
   getTokenRotation()
   getTokenRotation(id)
   getTokenRotation(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to retrieve the rotation angle.  Defaults to the [[Current_Token|Current Token]].}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   '''Result'''<br />
   The function returns the token's rotation as a numeric value measured in degrees.
   |example=
   Get the rotation for the four tokens shown below.
   <source lang="mtmacro" line>
   [h: switchToken("Mage")]
   [r: token.name] - [r: r = getTokenRotation()]<br>
   [h: switchToken("Elf")]
   [r: token.name] - [r: r = getTokenRotation()]<br>
   [h: switchToken("Hero")]
   [r: token.name] - [r: r = getTokenRotation()]<br>
   [h: switchToken("Troll")]
   [r: token.name] - [r: r = getTokenRotation()]</source>
   Returns:
   [[File:getTokenRotation.png|File:getTokenRotation.png]]
   |also=
   [[getTokenFacing|getTokenFacing]]

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
