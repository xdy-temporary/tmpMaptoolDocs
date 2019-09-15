.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=hasLightSource
   |version=1.3b48
   |description=
   Returns 1 if the [[Current_Token|Current Token]] has any [[LightSource:light_source|light source]]s that match the criteria passed in or 0 if there are no matches. If no arguments are passed to the function then it will return 1 if any [[LightSource:light_source|light source]] is on. If only the first argument is passed it will return 1 if any [[LightSource:light_source|light source]] of that [[LightSource:light_source_type|light source type]] is on. If both arguments are passed to the function it will return 1 if the [[LightSource:light_source|light source]] with the specified name and specified [[LightSource:light_source_type|light source type]] is on.

   |usage=
   <source lang="mtmacro" line>
   hasLightSource()
   hasLightSource(type)
   hasLightSource(type, name)
   hasLightSource(type, name, id)
   hasLightSource(type, name, id, mapname)
   </source>

   '''Parameters'''
   {{param|type|The [[LightSource:light_source_type|light source type]], (e.g. "Generic", "D20"). If "*" is entered, all light sources types are checked. Defaults to "*".}}
   {{param|name|the name of the [[LightSource:light_source|light source]]. If "*" is entered, all light sources names are checked. Defaults to "*".}}
   {{param|id|The token {{code|id}} of the token which is checked for light sources, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   Check to see if any light source is on.
   <source lang="mtmacro" line>
   [h: l = hasLightSource()]
   </source>

   Check to see if a "D20" lamp is on.
   <source lang="mtmacro" line>
   [h: l = hasLightSource("D20", "Lamp - 15")]
   </source>

   Check to see if any "D20" light source is on.
   <source lang="mtmacro" line>
   [h: l = hasLightSource("D20")
   </source>

   |changes=
   {{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options. Changed behavior if {{code|type}} or {{code|name}} are set to "*".}}

   }}

`Category:Light Function <Category:Light_Function>`__
