.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   | name=exposeFOW
   | version=1.3b76
   |trusted=true
   | description=
   Clears the Fog of War (FOW) for all '''selected''' tokens on the current map according to their sight settings. An optional {{code|mapName}} parameter allows exposure on maps other than the current map.  ''Note that unless the optional {{code|tokens}} parameter is provided there must be tokens selected on the map.''

   | usage=
   <source lang="mtmacro">
   exposeFOW()
   exposeFOW(mapname)
   exposeFOW(mapName,tokens)
   exposeFOW(mapName,tokens, delim)
   </source>
   '''Parameters'''
   {{param|mapname|Optional map name.}}
   {{param|tokens|Optional delimited string list or JSON array of tokens.}}
   {{param|delim|Delimiter for tokens parameter.  Defaults to ",".  Use "json" for a JSON array.}}

   | example=
   <source lang="mtmacro" line>
   <!-- Expose FoW for selected tokens on current map. -->
   [h: exposeFOW()]
   <!-- Expose FoW for selected tokens on the named map. -->
   [h: exposeFOW("Pit of Despair")]
   <!-- Expose FoW for indicated tokens on the named map. -->
   [h: exposeFOW("Pit of Despair", "Westley, Count Rugen")]
   <!-- Expose FoW for indicated tokens, in a list delimited by a colon (":"), on the named map. -->
   [h: exposeFOW("Pit of Despair", "Westley:Count Rugen", ":")])]
   <!-- Expose FoW for indicated tokens in a JSON array on the named map. -->
   [h: exposeFOW("Pit of Despair",'["Westley", "Count Rugen"]', "json")]
   </source>
   | changes=
   * '''1.5.4''' - Added tokens and delim parameters.

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:FoW <Category:FoW>`__
