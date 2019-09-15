.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenFacing
   |trusted=false
   |version=1.3b51
   |description=
   Gets the facing angle for the specified or current token.  Default facing is down or -90 degrees.  Zero degrees is along the X-axis to the right.

   |usage=
   <source lang="mtmacro" line>
   getTokenFacing()
   getTokenFacing(id)
   getTokenFacing(id, mapname)
   </source>
   '''Parameters'''
   {{param|id|The id of the token to get the facing from, defaults to the current token.}}{{TrustedParameter}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   '''Returns'''
   The angle in degrees or {{code|""}} if no facing has been set

   |example=
   <source lang="mtmacro" line>
   [h: switchToken("Mage")]
   [r: token.name]: [r: r = getTokenFacing()]<br>
   [h: switchToken("Elf")]
   [r: token.name]: [r: r = getTokenFacing()]<br>
   [h: switchToken("Hero")]
   [r: token.name]: [r: r = getTokenFacing()]<br>
   [h: switchToken("Troll")]
   [r: token.name]: [r: r = getTokenFacing()]
   </source>
   '''Returns:'''<br />
   [[File:getTokenFacing.png|File:getTokenFacing.png]]
   |also=
   [[getTokenRotation|getTokenRotation]]

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
