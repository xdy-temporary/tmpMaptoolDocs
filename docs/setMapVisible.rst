.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setMapVisible
   |version=1.4.0.1
   |trusted=true
   |description=
   Sets a maps visibility to players to {{true}} or {{false}}. If no map is specified the current map is selected.
   |usage=
   <source lang="mtmacro" line>
   setMapVisible(visible)
   setMapVisible(visible, mapName)
   </source>
   '''Parameters'''
   {{param|visible|Whether or not the map can be seen by players, {{true}} or {{false}}.}}
   {{param|mapName|A string containing the name of the Map.}}
   |examples=
   <source lang="mtmacro" line>
   [r:setMapVisible(1)]
   [r:setMapVisible(1, "Grasslands")]
   </source>
   }}

`Category:Map Function <Category:Map_Function>`__
