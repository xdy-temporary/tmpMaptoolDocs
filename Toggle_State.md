## Toggle State

This is a very simple macro that allows you to toggle the state of
selected tokens. It is potentially useful to a GM who has players that
can mark - simply set the name of the state at the beginning of the
macro. It is useful to have a different button (stored locally or in
campaign macros) for each player's mark. You can quickly select several
enemies when marking with a blast/burst power or for switching marks you
can select both the old mark and the new mark and it will toggle as
wanted.

Special thanks to zEal who made this macro for me.

``` mtmacro numberLines
[h: StateName = "Marked_red" ]
[h, foreach( Selected, getSelected("json") ):

setState(StateName,if(getState(StateName, Selected),0,1),Selected)

]

```

[Category:Cookbook](Category:Cookbook "wikilink")