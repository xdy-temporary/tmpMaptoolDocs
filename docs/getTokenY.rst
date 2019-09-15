.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenY
   |version=1.3b51
   |description=
   Gets the Y coordinate for a token.

   |usage=
   <source lang="mtmacro" line>
   getTokenY()
   </source>
   <source lang="mtmacro" line>
   getTokenY(units)
   </source>
   <source lang="mtmacro" line>
   getTokenY(units, id)
   </source>
   '''Parameters'''
   * {{code|units}} - If set to {{false}}, the coordinate is a location on the grid in number of ''cells''. Defaults to {{true}}, where the coordinate is in ''number of Pixels'' (in other words 0:distance in cells, 1: distance in pixels)'.
   * {{code|id}} - The id of the token to move, defaults to the [[Current_Token|Current Token]].

   '''Which coordinate is returned for tokens larger then one cell'''
   {{ProposedChange|The {{mark}}marked exception will disappear.}}
   * With the exception of {{mark}}one case the coordinates of the cell are given where the UPPER LEFT CORNER of the image of the token is in at that moment. 
   * {{mark}}The exception to this is when the token is 'Freesize' AND 'Snapped to Grid' AND '''NOT''' 'On Background Layer'. In that particular case the coordinates of the cell where the upper left corner of the FOOTPRINT (NOT image) of the token is at. The footprint can be recognized when you move the token on the Token layer, it will leave the white marker on the field. The footprint can be the same size as the image and it is if a preset size is used. With freesize however the size of the footprint is either the original size of the image OR when you have used a preset (e.g. 'large') it will have the size of the preset as footprint. 
   * Note that if you rotate the image such that the image is no longer in the upper left corner, the upper left corner of its '''native position''' is still returned as its coordinate. 

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
   {{func|moveToken}}, 
   {{func|getTokenX}},
   {{func|getZoom}},
   {{func|setZoom}}.
   }}

`Category:Distance Function <Category:Distance_Function>`__
