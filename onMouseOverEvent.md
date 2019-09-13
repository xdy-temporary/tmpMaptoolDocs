**This is a FAKE event**. You will need to create a macro and turn on
some settings in Maptool to emulate this.

This event can be simulated by turning on *"Show stat sheet on mouse
over"* in the [MapTool
Preferences](MapTool_Preferences#Tokens "wikilink"):

`   menu--> edit --> preferences --> Interactions --> 'Tokens' box: at the bottom --> check the checkbox`

And then creating a macro as a [campaign
property](Introduction_to_Properties "wikilink") e.g.:

`   *onMouseOverOnceVar:[macro("onMouseOver@lib:onMouseOver"):currentToken()]`

If you create a lib token  with the (self created) macro  then this
macro will be called EVERY time you hover your mouse over a token.

Note that this is extremely tricky and can result in system crashes or
lock-ups if done incorrectly. The point is that the macro is called
continuously when you hover over the token, so you have to take that
into account when creating the macro.

You can download a drop-in here
[1](http://forums.rptools.net/viewtopic.php?f=46&t=18542) (if the link
directs you to the 'forbidden' page then right mouse click on link and
copy link location and paste that in the browser) that shows two methods
that use this event. One method will run only once, this can be used
e.g. to setup a token after you dragged it onto the map. The other
method will run every time you hover over a token (but not continuously)

[Category:Event](Category:Event "wikilink")