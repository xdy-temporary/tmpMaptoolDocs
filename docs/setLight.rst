.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setLight
   |version=1.3b48
   |description=
   Sets the [[Map:light_source|light source]]s of the [[Token:Current_Token|Current Token]]. If the value is {{false}} then the [[Map:light_source|light source]] is turned off; otherwise, it is turned on.

   |usage=
   <source lang="mtmacro" line>
   setLight(type, name, value)
   setLight(type, name, value, id)
   setLight(type, name, value, id, mapname)
   </source>

   '''Parameters'''
   {{param|type|The [[LightSource:light_source_type|light source type]], (e.g. "Generic", "D20").}}
   {{param|name|The name of the [[LightSource:light_source|light source]].}}
   {{param|value|If {{true}} sets the light on, if {{false}} turns it off.}}
   {{param|id|The token {{code|id}} of the token to change the light sources, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   <source lang="mtmacro" line>
   [h: setLight("D20", "Candle - 5", 1)]
   </source>

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}

   }}

`Category:Light Function <Category:Light_Function>`__
