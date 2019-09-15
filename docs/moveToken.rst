.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=moveToken
   |version=1.3b51
   |description=
   Move a token to a new location.

   |usage=
   <source lang="mtmacro" line>
   moveToken(x, y)
   moveToken(x, y, units)
   moveToken(x, y, units, id)
   </source>
   '''Parameters'''
   * {{code|x}} - The X coordinate to move the token to.
   * {{code|y}} - The Y coordinate to move the token to.
   * {{code|units}} - If set to {{false}}, the coordinates are a location on the grid in '''cells'''. Defaults to {{true}}, where the coordinates are in ''Distance Per Cell'' '''pixels'''.
   * {{code|id}} - The id [[Macros:Variables:string|string]] of the token to move, defaults to the [[Current_Token|Current Token]].{{TrustedParameter}}
    
   <!-- The 'nbsp' is needed to close the DIV -->
   |examples=
   Moves the [[Current_Token|Current Token]] down {{code|5}} '''units''', and left {{code|10}} '''units'''.
   <source lang="mtmacro" line>
   [h: CurrentX = getTokenX()]
   [h: CurrentY = getTokenY()]
   [h: NewX = CurrentX + 5]
   [h: NewY = CurrentY - 10]
   [h: moveToken(NewX, NewY)]
   </source>

   Moves the [[Current_Token|Current Token]] down {{code|5}} '''cells''', and left {{code|10}} '''cells'''.
   <source lang="mtmacro" line>
   [h: CurrentX = getTokenX(0)]
   [h: CurrentY = getTokenY(0)]
   [h: NewX = CurrentX + 5]
   [h: NewY = CurrentY - 10]
   [h: moveToken(NewX, NewY, 0)]
   </source>

   |also=
   {{func|getTokenX}}, 
   {{func|getTokenY}}

   }}

`Category:Token Function <Category:Token_Function>`__
