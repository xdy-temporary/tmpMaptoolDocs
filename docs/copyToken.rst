.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=copyToken
   |trusted=true
   |version=1.3b51
   |description=Creates one or more copies of a [[Token|Token]] and returns the id of the created copy. This function is used to copy [[Token|Token]]s into the current map, the [[Token|Token]]s you are making
   copies of can reside on any map. '''You can not make any modifications to the newly created [[Token|Token]]s in the macro that creates them'''. Any changes made to the newly created token are reverted as soon as the macro ends!
   As of b54 there is a new parameter that allows you to make some changes to the new tokens.

   '''Note:''' below you can find several methods on how to make changes to the newly created 


   |usage=
   <source lang="mtmacro" line>
   copyToken(id)
   copyToken(id, numCopies)
   copyToken(id, numCopies, fromMap)
   copyToken(id, numCopies, fromMap, updates)
   newId = copyToken(id, numCopies, fromMap, updates)
   </source>


   ===Parameters===
   {{param|id|The id or name of the token to copy.}}
   {{param|numCopies|The number of copies to create, defaults to {{code|1}} }}
   {{param|fromMap|The name of the map to copy from, defaults to the current map.}}
   {{param|updates| a [[JSON_Object|JSON Object]] that contains updates to be made to the copied [[Token|Token]]s.}}

   You can use an empty string ("") for {{code|fromMap}} for the current map as of b54.


   The return type of this function is determined by the number of copies that you are making. If you are only creating a single
   copy of the token then a string containing the [[Token|Token]]s id, if you are making more than one copy then a [[JSON_Array|JSON Array]]
   containing the [[Token|Token]] ids of all the newly created [[Token|Token]]s is returned.


   ===Updates parameter===

   {{code|updates}} is a [[JSON_Object|JSON Object]] that can contain one or more of the following fields.  Field names are case-sensitive.
   * {{code|name}} - The name of the new [[Token|Token]].
   * {{code|label}} - The label for the new [[Token|Token]].
   * {{code|gmName}} - The GM name for the new [[Token|Token]].
   * {{code|layer}} - The layer for the new [[Token|Token]].
   * {{code|x}} - The X Co-ordinate for the new [[Token|Token]].  Default is {{code|0}}.
   * {{code|y}} - The Y Co-ordinate for the new [[Token|Token]].  Default is {{code|0}}.
   * {{code|useDistance}} - {{code|1}} (true) or {{code|0}} (false).  Determines if the "Distance Per Cell" measurement for the map is used for the x,y coordinates.  Unused if neither {{code|x}} nor {{code|y}} is specified.  Default is false.  Use {{code|1}} (true) for tokens that are not snap-to-grid and must be placed by pixel position instead of grid cell position.
   * {{code|facing}} - Sets the facing for the [[Token|Token]]. If the [[Token|Token]] is on the background or object layer this sets the rotation.
   * {{code|size}} - Sets the size of the [[Token|Token]].  The list of sizes is dependent on the type of grid.
   * {{code|delta}} - {{code|1}} (true) or {{code|0}} (false).  Indicates whether the x,y coordinates are relative to the position of the original token.  '''Added in 1.3b77.'''
   * {{code|tokenImage}} / {{code|portraitImage}} / {{code|handoutImage}} - Changes the coresponding image. Value can be either an assetId or an image token name. '''Added in 1.3b77.'''

   The values for all of these fields are evaluated so all text within {{code|{} }} or {{code|[]}} goes through the standard macro processing.  There is currently no way to modify the new token from inside these macro commands, however.

   When the name is not changed using the {{code|updates}} parameter, the new name for the token follows the naming method for cut and paste.
   This function can copy [[Token|Token]]s in the token, hidden, object, and background layers.  If you do not override the destination using the 
   {{code|layer}} field of {{code|updates}} then the new copies are made in the same layer as the source.  Likewise if {{code|x}} and {{code|y}}
   are not specified then these locations are the same as the source.


   ===How to make additional changes to the newly created token===

   As said, ANY changes made to the new token will be reverted as soon as the macro ends. However there are a couple of methods to do it anyway.

   1 The most reliable and straightforward method is to change the ORIGINAL token first and then copy it. You *can* revert the changes to the original after the copyToken. However if the original token is not on the same map then you can't immediately change the original. To solve that here some methods:

   a. The best methods in that case is to {{func|moveTokenFromMap}} to the current map and then {{func|moveTokenToMap}} back. 

   b. You could also use {{func|setCurrentMap}}) to go to the 'original' map, change the token and switch back, that however will result in a minor flicker on screen. 

   c. A final alternative is adding the 'lib:' prefix to the original, that way its properties are accessible throughout all maps

   2. The simplest method is by creating an interrupt in the macro after the copies have been made. This is simply done with the use of {{func|input}}. This however will result in a pop-up on screen which you have to click away so the macro can continue with the update. 

   3. Another (not always working method) is to make changes to the created tokens done by a second 'deferred' macro that is called after the copies have been created. Look for [[execLink|execLink]] for calling a macro ''deferred''.


   ==examples==
   Make a single copy of the Hero from the current map.
   <source lang="mtmacro" line>
   [h: copyToken("Hero")]
   </source>

   Make a single copy of the Hero from another map.
   <source lang="mtmacro" line>
   [h: copyToken("Hero", 1, "Green Room")]
   </source>

   Or if you are playing paranoia and want to create six clones.
   <source lang="mtmacro" line>
   [h: copyToken("Hero", 6, "Clone Vat")]
   </source>

   But as a PC the new tokens don't get new names so we could give each of them a new name in b54+ using the following.
   <source lang="mtmacro" line>
   [h: cloneNo = 0]
   [h: updates = "{ 
                    name: 'Hero Clone - [r: cloneNo = cloneNo + 1]'
                  }"
   ]
   [h: cloneNo = 0]
   [h: copyToken("Hero", 6, "Clone Vat", updates)]
   </source>

   This will copy all our clones to the current map but they are all on top of each other, to line them up
   <source lang="mtmacro" line>
   [h: cloneNo = 0]
   [h: x = 0]
   [h: updates = "{ 
                    name: 'Hero Clone - [r: cloneNo = cloneNo + 1]',
                    x: '[r: x = x + 2]',
                    y: 0
                  }"
   ]
   [h: cloneNo = 0]
   [h: copyToken("Hero", 6, "Clone Vat", updates)]
   </source>

   Or combining rotation
   <source lang="mtmacro" line>
   [h: cloneNo = 0]
   [h: x = 0]
   [h: facing = 0]
   [h: updates = "{ 
                    name: 'Hero Clone - [r: cloneNo = cloneNo + 1]',
                    x: '[r: x = x + 2]',
                    y: 0,
                    facing: '[r: facing = facing + 40]'
                  }"
   ]
   [h: cloneNo = 0]
   [h: copyToken("Hero", 6, "Clone Vat", updates)]
   </source>

   And now we have tumbling clones:

   [[Image:TumblingClones.jpeg|frame]]

   The source token was configured as a Top Down token for this effect, otherwise the {{code|facing}} setting would produce a facing arrow
   for [[Token|Token]]s on the token or hidden layers.

   [[Image:PointingClones.jpeg|frame]]

   This example shows using the new {{code|delta}} parameter available in '''1.3b77'''.  Specifying {{code|true}} means all x,y coordinates are treated as offsets from the original token.  They are measured in grid cells if {{code|useDistance}} is false (the default) or in pixels if {{code|true}}.

   <source lang="mtmacro" line>
   [h: x = 0]
   [h: updates = "{ 
       x: '[r: x = x + 2]',
       delta: 1,
   }" ]
   [h: copyToken(currentToken(), 3, "", updates)]
   </source>

   Make three copies of the currently selected token on the current map.  Place the first copy two grid cells to the right of the original token.  (Note that the trailing comma after {{code|delta: 1}} is ignored by MapTool.)

   ==examples of updates after copy==
   Simplest method:
   <source lang="mtmacro" line>
   [h:id=copyToken("Hero")]
   [h:input("junk|This interruption is required to create the new token. Click ok to continue.|Message |LABEL")]
   [h:setProperty("Strength", 3d6,id)]
   </source>

   Straightforward method:
   <source lang="mtmacro" line>
   [h:moveTokenFromMap("Hero", "Grasslands")]
   [h:setProperty("Strength", 3d6, "Hero")]
   [h:moveTokenToMap("Hero", "Grasslands")]
   [h:copyToken("Hero", 1, "Grasslands")]
   </source>

   Fancy method that leave the original token unchanged
   <source lang="mtmacro" line>
   [h:moveTokenFromMap("Hero", "Grasslands")]
   <!-- swap from name to token id as tokens with the same name will soon exist -->
   [h:origId = findToken("Hero")]
   <!-- copy original with same name -->
   [h:origCopyId = copyToken("Hero", 1, "", "{name: 'Hero'}")]
   <!-- update original with new properties -->
   [h:setProperty("Strength", 3d6, origId)]
   <!-- copy and then delete original -->
   [h:copyToken(origId, 1)]
   [h:removeToken(origId)]
   <!-- move the copy from BEFORE the changes back to the original map -->
   [h:moveTokenToMap(origCopyId, "Grasslands")]</source>

   ==also==
   {{func|moveTokenToMap}}, 
   {{func|moveTokenFrom}}

   ==changes==
   {{change|1.3b54|Added optional {{code|updates}} parameter.}}
   {{change|1.3b77|Added {{code|tokenImage}}, {{code|portraitImage}}, {{code|handoutImage}}, and {{code|delta}} to {{code|updates}}.}}
   }}

`Category:Token Function <Category:Token_Function>`__
