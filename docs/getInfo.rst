.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getInfo
   |version=1.3b69
   |description=
   Returns a [[JSON_Object|JSON Object]] with lots of information about a specified topic.

   |usage=
   <source lang="mtmacro" line>
   getInfo(topic)
   </source>
   '''Parameter'''
   {{param|topic|A string specifying the topic of the retrieved information. Can be {{code|"map"}}, {{code|"client"}}, {{code|"server"}}, or {{code|"campaign"}}.}}

   |examples=

   ===Retrieve {{code|map}} Information===

   <source lang="mtmacro" line>
   <!-- print the JSON Object about the current map to the chat window -->
   <pre>
   [r: json.indent(getInfo("map"), 2)]
   </pre>
   </source>

   Sample output:
   <pre>map
   {
     "id": "0A00010782897D2C3700000008000102",
     "image y scale": 1,
     "height": 0,
     "largest Z order": 2,
     "width": 0,
     "name": "Grasslands",
     "creation time": 1276351711618,
     "grid":     {
       "cell offset height": 0,
       "cell width": 50,
       "color": "ff000000",
       "cell offset width": 0,
       "units per cell": 5,
       "cell height": 50,
      "second dimension": 0,
       "type": "Square",
       "x offset": 0,
       "y offset": 0,
       "size": 50
     },
     "vision type": "off",
     "image x scale": 1,
     "player visible": 1
   }
   </pre>

   ===Retrieve {{code|client}} Information===

   <source lang="mtmacro" line>
   <!-- print the JSON Object about client information to the chat window -->
   <pre>
   [r: json.indent(getInfo("client"), 2)]
   </pre>
   </source>

   Sample output:
   <pre>client
   {
     "movement metric": "ONE_TWO_ONE",
     "library tokens": {
       "Lib:cifMacroIO": "unknown"
     },
     "portrait size": 175,
     "user defined functions": [
       "getMacroGroups",
        "redefined_1_getMacroGroups",
        "l.decode",
        "redefined_0_l.decode"
     ],
     "timeDate": "2010-10-13 19:03:38",
     "timeInMs": 1286989418105,
     "show stat sheet": true,
     "face vertex": 1,
     "version": "DEVELOPMENT",
     "face edge": 1
   }
   </pre>

   '''Note:'''
   The {{code|getInfo("client")}} function returns the names of all Lib: tokens. As a bonus if the Lib: token has a property called {{code|libversion}}, the value of this property will be reported as the value.

   ===Retrieve {{code|server}} Information===

   <source lang="mtmacro" line>
   <!-- print the JSON Object about server information to the chat window -->
   <pre>
   [r: json.indent(getInfo("server"), 2)]
   </pre>
   </source>
   {{ProposedChange|* '''1.3b90''' - Added value {{code|"gm"}} to {{code|server}} return value that holds an array of logged in game masters}}
   Sample output:
   <pre>server
   {
     "initiative owner permissions": 0,
     "players can reveal": 0,
     "movement locked": 0,
     "tooltips for default roll format": 1,
     "individual views": 0,
     "players receive campaign macros": 0,
     "strict token management": 0,
     "restricted impersonation": 0
   }
   </pre>

   ===Retrieve {{code|campaign}} Information===

   <source lang="mtmacro" line>
   <!-- print the JSON Object about the campaign to the chat window -->
   <pre>
   [r: json.indent(getInfo("campaign"), 2)]
   </pre>
   </source>


   Sample output:
   <pre>campaign
   {
       "tables": [],
       "initiative owner permissions": 1,
       "id": "C0A8001E7F7E199B0B0000008008001E",
       "sight": {
       "Darkvision": {
           "distance": 0,
           "arc": 0,
           "shape": "CIRCLE",
           "type": 0,
           "multiplier": 1 },
       "Normal Vision - Short Range": {
           "distance": 0,
           "arc": 0,
           "shape": "CIRCLE",
           "type": 0,
           "multiplier": 1 },
       "Normal": {
           "distance": 0,
           "arc": 0,
           "shape": "CIRCLE",
           "type": 0,
           "multiplier": 1 },
       "Square Vision": {
           "distance": 0,
           "arc": 0,
           "shape": "SQUARE",
           "type": 0,
           "multiplier": 1 },
       "Lowlight": {
           "distance": 0,
           "arc": 0,
           "shape": "CIRCLE",
           "type": 0,
           "multiplier": 2 },
       "Conic Vision": {
           "distance": 120,
           "arc": 120,
           "shape": "CONE",
           "type": 0,
           "multiplier": 1 }
       },
       "initiative movement locked": 1,
       "light sources": {
       "D20": [
           {
           "name": "Lantern, Hooded - 30",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 30,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 60,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 60 },
           {
           "name": "Candle - 5",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 5,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 10,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 10 },
           {
           "name": "Lamp - 15",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 15,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 30,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 30 },
           {
           "name": "Torch - 20",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 20,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 40,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 40 },
           {
           "name": "Sunrod - 30",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 30,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 60,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 60 },
           {
           "name": "Everburning - 20",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 20,
               "shape": null },
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": {"color":1677721600},
               "radius": 40,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 40 } ],
       "Generic": [
           {
           "name": "5",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 5,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 5 },
           {
           "name": "40",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 40,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 40 },
           {
           "name": "20",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 20,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 20 },
           {
           "name": "60",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 60,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 60 },
           {
           "name": "15",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 15,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 15 },
           {
           "name": "30",
           "light segments": [
               {
               "GM": false,
               "arcAngle": 360,
               "facingOffset": 0,
               "ownerOnly": false,
               "paint": null,
               "radius": 30,
               "shape": null } ],
           "type": "NORMAL",
           "max range": 30 } ] },
       "bars": {
       "no group": [
           {
           "increment": 0,
           "side": "TOP",
           "name": "Health" } ] },
       "states": {
       "no group": [
           "Incapacitated",
           "Disabled",
           "Other2",
           "Other",
           "Other3",
           "Prone",
           "Hidden",
           "Dead",
           "Other4" ] },
       "remote repository": [],
       "zones": {
       "Grasslands": "C0A8001E7E7F199B0C0000008008001E" }
   }
   </pre>

   |changes=
   * '''1.3b70''' - Added "{{code|campaign"}} option for {{code|topic}}
   * '''1.3b76''' - Added values {{code|"timeInMS"}} and "{{code|timeDate"}} to both {{code|client}} and {{code|server}} return values
   {{ProposedChange|* '''1.3b90''' - Added value {{code|"gm"}} to {{code|server}} return value that holds an array of logged in game masters}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
