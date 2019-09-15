.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage, and clearer description.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=moveTokenFrom
   |trusted=true
   |version=1.3b54
   |description=
   Moves tokens from a specified map to the current map.

   |usage=
   <source lang="mtmacro" line>
   moveTokenFromMap(id, map, x, y, z)
   </source>
   '''Parameters'''
   {{param|id|The token {{code|id}} or a [[JSON_Array|JSON Array]] of token {{code|id}}s of the token/s to move.}}
   {{param|map|A string containing the name of the map that the token is moved from.}}
   {{param|x|The {{code|X}} coordinate of the current map that the token should be moved to.}}
   {{param|y|The {{code|Y}} coordinate of the current map that the token should be moved to.}}
   {{param|z|The z-order that the token should have after being moved.}}

   |also=
   {{func|moveTokenToMap}}

   }}

`Category:Token Function <Category:Token_Function>`__
