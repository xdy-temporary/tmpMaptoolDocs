### \[ \] Display to Specific Player Option

<div>

• **Introduced in version 1.3.b58**

</div>

**\[w("name"): \]**, **\[whisper("name"): \]** evaluates the text after
the ':' but only displays the results to the specific named user, such
as:

``` mtmacro numberLines
Everyone can see this [w("bob"): "but only Bob can see this"]
```

can also take more than one player name as an argument:

``` mtmacro numberLines
[w("Fred", "Joe"): d20]
```

It can also take a JSON list containing player names:

``` mtmacro numberLines
[h: names = json.fromList("Fred, Joe")]
[w(names): d20]
```

This roll option may be combined with the , , , and  options. Blank
messages will not be shown to a certain user if an entire message is
invisible to that user due to these roll options or the  roll option.

[Category:Roll Option](Category:Roll_Option "wikilink")
[Category:Display Roll Option](Category:Display_Roll_Option "wikilink")