.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction

   |name=isSnapToGrid

   |version=1.3b69

   |description=

   Returns {{true}} if a [[Token|Token]] is snapped to grid or {{false}} if it is not.




   |usage=

   <source lang="mtmacro" line>
   isSnapToGrid()
   isSnapToGrid(id)
   isSnapToGrid(id, mapname)
   </source>

   '''Parameter'''

   {{param|id|The token {{code|id}} of the token which has its snapToGrid status checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   <source lang="mtmacro" line>
   [h: snap=isSnapToGrid()]</source>

   |also=
   {{func|setTokenSnapToGrid}}
   }}

\|changes=

`Category:Token Function <Category:Token_Function>`__
