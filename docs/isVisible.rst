.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=isVisible
   |version=1.3b69
   |description=
   Check whether a point on the map is visible from a token or not.
   It returns 1 is the token is visible, 0 otherwise. This vision is based off of the impersonated token.
   |usage=
   <source lang="mtmacro" line>
   isVisible(x,y)
   </source>
   <source lang="mtmacro" line>
   isVisible(x,y,id)
   </source>
   '''Parameter'''
   {{param|x|Then tokens x coordinate. Always in map units, not grid .}}
   {{param|y|Then tokens x coordinate. Always in map units, not grid .}}
   {{param|id|The check for visibility is performed from token {{code|id}}.  {{TrustedParameter}}
   }}

   |example=
   A simple example for testing out {{code|isVisible()}}. Drop the default tokens "Hero" and "Troll" on a map. Make sure "Hero" has sight (make him PC or set sight manually). You can then execute the following code as a campaign macro to check if the Hero can see the Troll.
   <source lang="mtmacro" line>
   <!-- lets check if token1 can see token2 -->
   [h: token1 = "Hero"]
   [h: id1 = findToken(token1)]

   [h: token2 = "Troll"]
   [h: id2 = findToken(token2)]

   <!-- get the map coordinates of token2 -->
   <!-- i want to check if the center of the occupied cell can be seen -->
   <!-- getTokenX/Y retrieves the top-left corner, so -->
   <!-- in a 50 pixel grid the center is offset by 25 pixel -->
   [h: x = getTokenX(1, id2)+25]
   [h: y = getTokenY(1, id2)+25]

   <!-- and final the check for visiblity -->
   [r:getName(id1)] <b>[r, if(isVisible(x,y, id1)): "can"; "cannot"]</b> see [r:getName(id2)].
   </source>


   }}

`Category:Token Function <Category:Token_Function>`__
