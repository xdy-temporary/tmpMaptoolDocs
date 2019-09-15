.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setCurrentMap
   |version=1.3b60
   |description=
   Designates the given map as the current one, allowing initiative to be moved from map to map. 

   '''WARNING:'''  This function changes an internal variable used by MapTool to keep track of which map is current and this change takes place immediately.  However, changes to tokens are queued up and only occur when the macro finishes execution (well, sort of).  The end result is that if a token is being modified on map "A" and your macro calls {{func|setCurrentMap}} to switch to map "B", when the macro finishes and the token changes are executed they will be processing a token on map B!  If there was no such token on map B a new one will be created, thus mysteriously duplicating tokens!

   Therefore, do NOT modify any token properties, states, names, notes, or any other token-specific values after calling {{func|setCurrentMap}}.  Or make sure that the first thing your macro does is call {{func|setCurrentMap}} so that all tokens accessed later will be on the map that is current when the macro finishes.

   Search http://forums.rptools.net/ for {{code|setCurrentMap}} to find some discussion threads on this topic.

   |usage=
   <source lang="mtmacro">
   setCurrentMap(mapName)
   </source>
   |examples=
   <source lang="mtmacro" line>
   [h: status = input("NewMap|" + getAllMapNames() + "|Map to switch to|LIST|VALUE=STRING")]
   [h:abort(status)]
   [h:setCurrentMap(NewMap)]
   </source>
   |also=
   {{func|getAllMapNames}} {{func|getVisibleMapNames}}

   }}

`Category:Map Function <Category:Map_Function>`__
