.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=copyMap
   |version=1.4.0.1
   |trusted=true
   |description=
   Creates a copy of an specified map, with the new map name. Returns the name of the new map.
   |usage=
   <source lang="mtmacro" line>
   copyMap(existingMapName, newMapName)
   </source>
   '''Parameters'''
   {{param|existingMapName|The name of the existing map you wish to copy.}}
   {{param|newMapName|A string containing the name of the new copy.}}
   |examples=
   <source lang="mtmacro" line>
   [h:copyMap("BaseMap","Tower")]
   [h:setMapVisible(1,"Tower")]
   </source>
   }}

`Category:Map Function <Category:Map_Function>`__
