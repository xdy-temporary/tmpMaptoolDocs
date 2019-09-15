.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=isGM
   |version=1.3b48
   |description=
   Returns {{true}} if the player is a GM or {{false}} if they are not.

   |usage=
   <source lang="mtmacro" line>
   isGM()
   </source>

   <source lang="mtmacro" line>
   isGM(player)
   </source>'''Parameters'''
   {{param|player|player's name as a string to check if he is a GM or not.}}

   |examples=
   '''1. Test to see if current player is a GM.'''

   <source lang="mtmacro" line>
   I am a [r,if(isGM()): "GM"; "Player"]
   </source>


   '''2. Display a list of GMs.'''

   <source lang="mtmacro">
   [H: allPlayers = getAllPlayerNames("json")]
   [H: GMList = "[]"]
   [H: foreach(player,allPlayers), code: {
      [H, if(isGM(player)): GMList = json.append(GMList,player)]
   }]
   [R, if(! json.isEmpty(GMList)): "GM List: " + json.toList(GMList); "No players are listed as GM"]
   </source>


   |changes=
   *  '''b91''' - Added {{code|player}} parameter}}

`Category:Permission Function <Category:Permission_Function>`__
