.. contents::
   :depth: 3
..

This macro allows a player to pick-up a NPC among those he can currently
see. Note that this is about the player's view and not the currently
selected token's view. You may then store the target's name in the
token's properties to ease further actions.

Basically, the macro gets the list of all NPCs available (with ) and the
list of all visible tokens (with ). Then, the intersection will provide
visible NPCs.

Macro
=====

**1.3b53+**

.. raw:: html

   <hr>

.. code:: mtmacro
   :number-lines:

   /self 
   [h: lsVisibleNpc = json.intersection( getNPCNames("json"), getVisibleTokenNames("json") )]

   // Abort if no target found (intersection returned an empty list)
   [h: assert(json.length(lsVisibleNpc), "No visible NPC", 0)]

   // UI: popup a list for selection
   [h: input("index|"+json.toList(lsVisibleNpc)+"|My target is|LIST") ]

   // Retrieve the first element, so we only get the name (and not ["name"])
   [h: currentTgt = json.get(lsVisibleNpc, index) ]

   // Display message to be sure of what has just been done
   Current target : {currentTgt}

`Category:Cookbook <Category:Cookbook>`__
