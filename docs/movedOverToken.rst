.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=movedOverToken
   |version=1.3.b74
   |description=
   Is used to check if the location of the target {{code|token}} is in an array of cell coordinates like the one received from {{func|getLastPath}} or the [[onTokenMove|onTokenMove]] event's {{code|macro.args}}.
    
   <!-- The 'nbsp' is needed to close the DIV -->
   |usage=
   <source lang="mtmacro">
   movedOverToken(token)
   movedOverToken(token, lastPath)
   </source>
   '''Parameters'''
   {{param|token|The target token to compare the }}
   {{param|lastPath|Optional JSON array of coordinate pairs.  If not supplied will use the last path of the current token.}}

   '''Returns'''

   A JSON array of cell coordinates where the moving token crossed the target token.
   <source lang="javascript">
   [{"x":900,"y":400},{"x":900,"y":350},{"x":900,"y":300}]
   </source>

   |example=
   Check if the current token moved over a token called "Pit Trap".
   <source lang="mtmacro" line>
   [r: movedOverToken("Pit Trap")]
   </source>
   '''Returns:'''
   An array of coordinate pairs. In this case, just one.
   <source lang="mtmacro">
   [{"x":550,"y":250}]
   </source>

   Count how many cells of caltrops the current token moved through.
   <source lang="mtmacro" line>
   [h: lastPath = getLastPath(1)]
   [h: locations = movedOverToken("Caltrops",lastPath)]
   Token moved over [r: json.length(locations)] caltrops.
   </source>
   '''Returns:'''
   A count of the cells of the ''Caltrops'' token the current token moved over.
   <source lang="mtmacro">
   Token moved over 3 caltrops.
   </source>

   |also=
   {{func|getLastPath}} {{func|movedOverPoints}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
