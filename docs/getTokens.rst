.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokens
   |trusted=true
   |version=1.3b48
   |description=
   Gets a list containing the ids of all the tokens on the current map, or all the tokens that match the specified conditions. The type of the value returned depends on the delimiter parameter. 

   Note: apparently the order of the list that getTokens() returns is also the z-order of the tokens, where the lowest z-order is the first in the list or array that is returned!

   |usage=
   <source lang="mtmacro" line>
   getTokens()
   </source>
   <source lang="mtmacro" line>
   getTokens(delim)
   </source>
   <source lang="mtmacro" line>
   getTokens(delim, conditions)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to sepearate the values in the String List that is returned, defaults to {{code|","}}. If {{code|"json"}} is specified, a JSON array is returned instead of a String List.}}
   {{param|conditions|A JSON object that contains various conditions that the tokens must fullfill. All conditions are optional.
   ** {{code|setStates}} - A JSON array of states the token must have.  Any token which does not contain all of these states in the {{code|true}} condition will be removed from the returned list.
   ** {{code|unsetStates}} - A JSON array of states the token must '''not''' have.
   ** {{code|npc}} - If the token must be a NPC, set to {{true}} or {{false}}.
   ** {{code|pc}} - If the token must be a PC, set to {{true}} or {{false}}.
   ** {{code|selected}} - If the token must be selected, set to {{true}} or {{false}}.
   ** {{code|impersonated}} - If the token must be impersonated, set to {{true}} or {{false}}.
   ** {{code|current}} - If the token must be the current token, set to {{true}} or {{false}}.
   ** {{code|owned}} - If the token must be owned by the current player, set to {{true}} or {{false}}.
   ** {{code|visible}} - If the token must be visible to players, set to {{true}} or {{false}}.
   *** <u>note</u>: '''GMs will be able to see everything, to test if a token is visible to a player with this function, you must have "Show as a Player" enabled. In addition, this appears to only affect the "Visible to players" flag - VBL and Fog of War do not seem to affect this'''.
   ** {{code|layer}} - A JSON array of layer names, or a single layer name as a string.  Only tokens on one of the listed layers will be returned. By default, tokens on the Token and Hidden layers are returned.(added in '''1.3b77''')
   ** {{code|range}} - A JSON object with range conditions, all range conditions are optional.
   *** {{code|token}} - The id or name of the source token that the distance is measured from, defaults to the current token. 
   **** <u>note</u>: '''token parameter cannot be unset or empty unless you are calling your macro from a macroLink and aren't impersonating a token'''.
   *** {{code|distancePerCell}} - If the Distance Per Cell multiplier should be used, set to {{true}} or {{false}}.
   *** {{code|from}} - A number specifying the minimum range that a token needs to be from the source.
   *** {{code|upto}} - A number specifying the maximum range that a token can be from the source.
   *** {{code|metric}} - The distance metric to use, if it is not specified the default from the users preferences is used.
   ** {{code|area}} - A JSON object containing specific area information.
   *** {{code|token}} - An optional field that contain the name or id of the token that resides at the center of the area. Defaults to the current token.
   *** {{code|offsets}} - A JSON array of JSON objects that specify each individual cell that make up the area.
   **** {{code|x}} - The relative {{code|x}} position of the cell in relation to the {{code|token}} field. Measured in cells.
   **** {{code|y}} - The relative {{code|y}} position of the cell in relation to the {{code|token}} field. Measured in cells.}}


   The movement metric in range specifies the movement metric use, the metric can be one of the following strings:
   :* {{code|NO_GRID}} - The grid is ignored and straight line distance between the tokens is returned.
   :* {{code|ONE_TWO_ONE}} - First Diagonal movement costs 1, second 2, and so on (Square grid only).
   :* {{code|ONE_ONE_ONE}} - Diagonal movement costs a single square (Square grid only).
   :* {{code|MANHATTAN}} - Diagonal movement costs 2 (Square grid only).
   :* {{code|NO_DIAGONALS}} - No diagonal movement is allowed (Square grid only).

   |example=

   *You can use the following code to print out the ids of all of the tokens on the current map:
   <source lang="mtmacro" line>
   [h: ids = getTokens()]
   [foreach(id, ids, "<br>"): id]
   </source><br />
   *Find ALL the tokens on ALL the layers on the map:
   <source lang="mtmacro" line>
   [r:getTokens(",", json.set("{}", "layer", json.append("[]","TOKEN","HIDDEN","OBJECT","BACKGROUND")))]
   </source><br />
   *Find and return a [[JSON_Array|JSON Array]] containing all NPC tokens that are with 2 squares or hexes of the selected token:
   <source lang="mtmacro" line>[h: cond = '{ "range": {"upto":2, "distancePerCell":0, "token":"' +getSelected()+ '"}, "npc":1}']
   [h: ids = getTokens("json", cond)]
   </source><br />
   *Modifying the above example to exclude dead tokens:
   <source lang="mtmacro" line>
   [h: cond = '{ "range": {"upto":2, "distancePerCell":0, "token":"' +getSelected()+ '"}, "npc":1, "unsetStates":["Dead"] }']
   [h: ids = getTokens("json", cond)]
   </source><br />
   *Get all of the non dead NPC tokens in the square above, below, left, and to the right of the token, using the {{code|area}} option:
   <source lang="mtmacro" line>
   [h: areaOffsets = '[ {x:1, y:0}, {x:0, y:1}, {x:-1, y:0}, {y:-1, x:0}]']
   [h: area = json.set("{}", "offsets", areaOffsets)]
   [h: cond = json.set("{}", "area", area, "npc", 1, "unsetState", "['Dead']")]
   [h: ids = getTokens("json", cond)]
   </source><br />
   *The same could be achieved using the {{code|range}} option with {{code|NO_DIAGONALS}} metric:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']
   [h: ids = getTokens("json", cond)]
   </source>
   Please note that it in general is bad practice to create JSON objects and arrays by hand. This makes your code very bug prone. The proper way is to build you JSON object through code.<br />
   E.g.:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']
   </source>
   can better be created with:
   <source lang="mtmacro" line>
   [h: cond = json.set("{}", "range", json.set("{}", "upto", 1, "distancePerCell", 0, "metric", "NO_DIAGONALS"), "npc", 1, "unsetStates", json.append("[]","Dead"))]
   </source>
   The big difference between the two methods is that doing it by hand, it's quite likely that when you make a mistake your code appears to 'work', that is you get no error reports, but only part of the conditions is met because you e.g. used <nowiki>''</nowiki> or "" where you should not have.<br />
   If you make a mistake in the automated method, there is a bigger chance you get an error report, allowing you to fix it. Of course typos like 'ragne' instead of 'range' won't trigger any errors. 

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added {{code|conditions}} parameter.}}
   {{change|1.3b55|Added {{code|metric}} option to {{code|range}} option in {{code|conditions}} parameter.}}
   }}

`Category:Find Function <Category:Find_Function>`__ `Category:Token
Function <Category:Token_Function>`__
