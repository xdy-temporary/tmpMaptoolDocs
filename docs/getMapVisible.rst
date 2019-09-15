.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMapVisible
   |version=1.4.0.1
   |description=
   Returns {{true}} or {{false}} indicating whether the specified map is visible to players. If no map is specified the current map is selected.
   |usage=
   <source lang="mtmacro" line>
   getMapVisible()
   getMapVisible(mapName)
   </source>
   '''Parameters'''
   {{param|mapName|Optional. A string containing the name of the Map.}}
   |examples=
   <source lang="mtmacro" line>
   [r:getMapVisible()]
   [r:getMapVisible("Grasslands")]
   </source>
   }}

`Category:Map Function <Category:Map_Function>`__
