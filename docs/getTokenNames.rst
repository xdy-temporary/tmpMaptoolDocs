.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenNames
   |trusted=true
   |version=1.3b48
   |description=
   Gets a list containing the names of all the [[Token|token]]s on the current [[Map|map]].

   |usage=
   <source lang="mtmacro" line>
   getTokenNames()
   </source>
   <source lang="mtmacro" line>
   getTokenNames(delim)
   </source>
   <source lang="mtmacro" line>
   getTokenNames(delim, conditions)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the String List that is returned, defaults to {{code|","}}. If {{code|"json"}} is specified, a JSON array is returned instead of a String List.}}
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
   *** <u>note</u>: GMs will be able to see everything, to test if a token is visible to a player with this function, you must have "Show as a Player" enabled. In addition, this appears to only affect the "visible to players" flag - VBL and Fog of War do not seem to affect this.
   ** {{code|layer}} - A JSON array of layer names, or a single layer name as a string.  Note that a token not on any of the listed layers will be removed from the list returned (added in '''1.3b77''')
   ** {{code|range}} - A JSON object with range conditions, all range conditions are optional.
   *** {{code|token}} - The id or name of the source token that the distance is measured from, defaults to the current token.
   **** <u>note</u>: this parameter is needed if you are calling your macro from a macroLink and aren't impersonating a token.
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
   *You can use the following code to print out the names of all of the tokens on the current map:
   <source lang="mtmacro" line>
   [h: names = getTokenNames()]
   [foreach(name, names, "<br>"): name]
   </source><br />
   *Find and return a [[JSON_Array|JSON Array]] containing all NPC tokens' names that are within 2 squares or hexes:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:2, distancePerCell:0}, npc:1 }']
   [h: names = getTokenNames("json", cond)]
   </source><br />
   *Modifying the above example to exclude dead tokens:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:2, distancePerCell:0}, npc:1, unsetStates:["Dead"] }']
   [h: names = getTokenNames("json", cond)]
   </source><br />
   *Get all of the non dead NPC tokens' names in the square above, below, left, and to the right of the token, using the {{code|area}} option:
   <source lang="mtmacro" line>
   [h: areaOffsets = '[ {x:1, y:0}, {x:0, y:1}, {x:-1, y:0}, {y:-1, x:0}]']
   [h: area = json.set("{}", "offsets", areaOffsets)]
   [h: cond = json.set("{}", "area", area, "npc", 1, "unsetState", "['Dead']")]
   [h: names = getTokenNames("json", cond)]
   </source><br />
   *The same could be achieved using the {{code|range}} option with {{code|NO_DIAGONALS}} metric:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']
   [h: names = getTokenNames("json", cond)]
   </source><br />
   *Get ALL tokens on a map:
   <source lang="mtmacro" line>
   [r:allToks = getTokenNames(",",'{layer:["TOKEN", "HIDDEN", "OBJECT", "BACKGROUND"]}')]
   </source>
   or better:
   <source lang="mtmacro" line>
   [r:getTokens(",", json.set("{}", "layer", json.append("[]","TOKEN","HIDDEN","OBJECT","BACKGROUND")))]
   </source>


   Please Note that it, in general, is bad practice to create json objects and arrays by hand. This makes your code very bug prone. The proper way is to build your json objects through code.<br />
   E.g.:
   <source lang="mtmacro" line>
   [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']
   </source>
   can better be created with
   <source lang="mtmacro" line>
   [h: cond = json.set("{}", "range", json.set("{}", "upto", 1, "distancePerCell", 0, "metric", "NO_DIAGONALS"), "npc", 1, "unsetStates", json.append("[]","Dead"))]
   </source>
   The big difference between the two methods is that, doing it by hand, it is quite likely that when you make a mistake your code appears to 'work', that is you get no error reports, but only part of the conditions are met because you e.g. used {{code|<nowiki>''</nowiki>}} or {{code|""}} where you should not have.<br />
   If you make a mistake in the automated method, there is a bigger chance you get an error report, allowing you to fix it. Of course typos like {{code|'ragne'}} instead of {{code|'range'}} won't trigger any errors. 

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added {{code|conditions}} parameter.}}

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Find
Function <Category:Find_Function>`__
