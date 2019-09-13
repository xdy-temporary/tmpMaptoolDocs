*... and all related stuff*

Recently a great new feature has been added to MapTool. This guide shall aide you to use it. Every time a token is moved (by the user) a specific macro is called. This macro can even cancel that move.

Events
======

Just like the new events are macros on a lib:token that have to be named like the event. Note that (and this is different to ) these events should be only defined on a single, unique Lib:token - doing otherwise can lead to unexpected behaviour. To state it clearly: there should not be two Lib:tokens in a campaign file with these macros on it at the same time.

onTokenMove
-----------

The event macro is called whenever any token on the TOKEN layer is moved via the user interface. So the event is NOT triggered for movement on the hidden,object or background layer. That tokens path is available as content of . The moved token is the token in context, so you can get its id with .

onMultipleTokensMove
--------------------

The event macro is **only** called when more than one tokens are moved at once. The contain a json array with all moved tokens ids. The is no token context.

Note that, before is actually called, is called for each single token.

If you use both events at the same time it is recommended that you use the variable in and abort if its &gt;1 and let handle it.

If you dont know what event to use you probably want to use .

How to set it up
================

1.  You need a [Library Token](Library_Token "wikilink"). You'll find some details if you follow that link, but its simply a token named “Lib:something” that is a NPC and visible to players.
2.  On this token you place macros. If you want to use the event *onTokenMove* you create a macro named on it.

Thats it. Yeah, it is so simple. For what you can really do with this you can see the examples below.

Special Variables
-----------------

There are some special variables that are needed or useful in context of these events.

[{{code](tokens.denyMove "wikilink") has to be set to to cancel the current movement.

[{{code](tokens.moveCount "wikilink") contains the number of tokens moved.

Paths
=====

In context of these events there will sometimes be specified or returned a path or a list of coordinates. These are in this specific format:

it is a json array containing json objects for each points. Each json object defines the keys and with the map coordinates.

``` mtmacro
[h: samplePath = json.append("",
    json.set("", "x", 50, "y", 50),
    json.set("", "x",  0, "y",  0)
)]


<!-- samplePath contains
[{"x":50,"y":50},{"x":0,"y":0}]
 -->
```

If you have to construct coordinate arrays by hand you can use a simple drop-in tool that you can download here: [rptools-forums: shapeBuilder](http://forums.rptools.net/viewtopic.php?p=180113#p180113)

Related Functions
=================

There is a number of functions that are very useful in combination with the onMove-events.

getLastPath()
-------------

returns the last path. Note that - if you use this in - it returns exactly the same as . *(requires b74+)*

movedOverPoints(arrayOfCoordinates)
-----------------------------------

returns an array of coordinates with all “hit” cells within a shape formed by the specified array of coordinates. *(requires b75+)*

movedOverToken(tokenName, \[lastPath\])
---------------------------------------

returns an array of coordinates with all “hit” cells where the moved token crosses the specified token. *(requires b74+)*

Note that before b77 the token must be specified by name - not id.

getMoveCount()
--------------

returns the calculated move cost according to the selected move metric. *(requires b76+)*

Examples
========

Lets now give you some simple examples for most commons use cases.

Traps/Teleporting
-----------------

An example of a trap macro:

``` mtmacro
[h:'<!-- this should be in onTokenMove -->']
[h:'<!--Routine for a Trap, trap is only triggered when the subject is moved on or over the Trap Token "Spear Trap"-->']
[h:'<!-- retrieve the path that the token has walked on -->']
[h:lastPath     = getLastPath(1)]
[h:'<!-- check if that path intersects with the trap token -->']
[h:trapPadTriggered = movedOverToken("Spear Trap",lastPath)]
[r, if(!json.isEmpty(trapPadTriggered)), CODE:{
    [h:'<!-- If so trigger the trap for that token, do note that this only works when ONE token is moved. -->']
    [h:me = getSelectedNames()]
    [h:switchToken(me)]

    [h:attackRoll = d20]
    [h:roll=1d6]
    [h,if(attackRoll > Dexterity):HP=HP-roll]
    [r,if(attackRoll > Dexterity):"You have triggered a trap and sustained "+roll+" hits.<br>"]
};{}]
```

An example of a Teleport macro:

``` mtmacro
[h:'<!-- Routine for a Teleport, this particular routine will move a token from a
         teleport token called "Start 1" to another token called "End 1"->']
[h:'<!-- Note that the big difference with the trap macro is that here you have to
         stop on the teleport token for it to be triggered, while the trap triggered
         when you move OVER OR ONTO the trap token ->']
[h: targetToken = currentToken()]
[h: lastPath    = getLastPath(1)]
[h: padName     = "Start 1"]
[h: teleporterTriggered = movedOverToken(padName,lastPath)]
[h,token(targetToken): currentLocation = json.set("{}","x",getTokenX(),"y",getTokenY())]

[h,if(json.contains(teleporterTriggered,currentLocation)), CODE:{
    [teleportEndName = replace(padName, "Start", "End")]
    [h:'<!-- This part makes sure that you end up on the same position on the end token as you started on the start token. E.g if you moved the PC onto the Upper left corner of "Start 1" then youll end up on the upper left corner of "End 1"" -->']

    [h:'<!-- Get the actual coordinates "Start 1" and "End 1" -->']
    [Token(padName):         startCentreX = getTokenX(1)]
    [Token(padName):         startCentreY = getTokenY(1)]
    [Token(teleportEndName): endCentreX   = getTokenX(1)]
    [Token(teleportEndName): endCentreY   = getTokenY(1)]

    [h:'<!-- Get the coordinates of the moved token -->']
    [h, Token(targetToken):CurrentX = getTokenX()]
    [h, Token(targetToken):CurrentY = getTokenY()]

    [h:'<!-- Calculate its relative position -->']
    [h:NewX = CurrentX + endCentreX - startCentreX]
    [h:NewY = CurrentY + endCentreY - startCentreY]

    [h:'<!-- move the token to the new location -->']
    [h, Token(targetToken):moveToken(NewX, Newy , 1 )]

    [h:'<!-- centre view on the tokens new position. -->']
    [goto(targetToken)]
};{}]
```

Please note that there already exists a drop-in [1](http://forums.rptools.net/viewtopic.php?f=46&t=16066) that facilitates Traps and Teleports (among other things), which you can find on the forum. The tricky part is to get multiple 'special pads' working next to each other in combination with multiple tokens move.

Movement cost tracking
----------------------

A often requested feature is to track allowed movement. With the new events we can do that.

The example expects the movement to be tracked with a property named *Movement*. You have to reset this property to some kind of *max movement* every round - eg by hand or by hooking it in your initiative handler.

``` mtmacro
<!-- this should be in onTokenMove -->
<!-- moved token is in context -->

<!-- get movement -->
[h: mov = getProperty("Movement")]
[h: usedMov = getMoveCount()]

<!-- deny move if not allowed, reduce mov prop otherwise -->
[r, if( mov >= usedMov ), code: {
    [h: mov = mov - usedMov]
    [h: setProperty("Movement", mov)]
};{
    [h: tokens.denyMove = 1]
    <span style="color:red;font-weight:bold;">Move limit exceeded.</span>
}]
```

Exposure of Fog on gridless maps
--------------------------------

Fog does not get cleared on gridless maps. But we can do this by using a simple onTokenMove-event.

``` mtmacro
<!-- this should be in onTokenMove -->
<!-- clear fog only if pc token moved -->
[h, if( isPC() ): exposeFOW()]
```

<Category:Cookbook>