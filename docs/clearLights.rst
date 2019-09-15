.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=clearLights
   |version=1.3b48
   |description=Turns off all of the [[LightSource:light_source|light source]]s for the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   clearLights()
   clearLights(id)
   clearLights(id, mapname)
   </source>

   '''Parameters'''
   {{param|id|The token {{code|id}} of the token for which to turn off all light sources, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   To turn off all of the light sources for the current token.
   <source lang="mtmacro" line>
   [h: clearLights()]
   </source>

   To turn off all the lights sources on the map you could run the following script, note you will have to be the GM or run it
   as part of a trusted macro.
   <source lang="mtmacro" line>
   Ok Kids lights out!
   [h,foreach(tok, getTokens()), code: { [token(tok): clearLights()]}]
   </source>

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}

   }}

`Category: Light Function <Category:_Light_Function>`__
