This event is triggered whenever the user selects a token.

As a frame-based event, a frame containing the event code has to be
opened.

## Set up

Create a frame that has this special html tag in it:

``` html4strict
<link rel='onChangeSelection' type='macro' href='macroLink'>
```

Replace  by an actual macroLinkText-call to a macro of your choice (the
returned value of ). A common practice is to call the frame opening
macro itself to actualize the content.

## See Also

[Forms tutorial\#Events](Forms_tutorial#Events "wikilink")

[Category:Event](Category:Event "wikilink")