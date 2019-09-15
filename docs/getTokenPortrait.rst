.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenPortrait
   |description=
   Returns the [[Asset_ID|asset id]] of the portrait image for the for the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   getTokenPortrait()
   getTokenPortrait(size)
   getTokenPortrait(size, id)
   getTokenPortrait(size, id, mapname)
   </source>

   '''Parameters'''
   {{param|size|OPTIONAL: The size the picture should be returned as. If a blank string "", no size adjustment is done. Defaults to "".}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to retrieve the token image, defaults to the [[Current_Token|Current Token]]. }}
   {{param|mapname|OPTIONAL: The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   To display the image for the current [[Token|Token]].
   <source lang="mtmacro" line>
   <img src='[r:getTokenPortrait()]'></img>
   </source>
   |changes={{change|1.5.4|Added {{code|id}} and {{code|mapname}} parameter options.}}
   }}

.. _version_notes:

Version Notes
=============

In versions before v1.3b51 an attempt to retrieve a portrait image when
none was present produced an error. In 1.3b51 and later builds the
function returns an empty string if no portrait is associated with the
image.

`Category:Token Function <Category:Token_Function>`__
