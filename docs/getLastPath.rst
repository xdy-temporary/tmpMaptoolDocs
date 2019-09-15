.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getLastPath
   |version=1.3.b74
   |description=
   Returns a json array of the coordinates of every step in the last movement path of the impersonated token. The coordinates are json objects with the keys {{code|x}} and {{code|y}}. 
   |usage=

   <source lang="mtmacro" line>
   [r: getLastPath()]
   [r: getLastPath(units)]
   </source>

   '''Parameters'''
   * {{code|units}} - If set to {{false}}, the coordinate is a location on the grid in ''cells''. Defaults to {{true}}, where the coordinate is in ''Distance Per Cell'' ''units'' (in other words 0:distance in cells, 1: distance in pixels)'.



   {{stub|example needed}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
