# How to show html code

Sometimes you want to show html code in chat or in a frame. Sadly
MapTool always interprets the html markup. This is sometimes unwanted,
especially if you try to debug complex output.

Luckily its quite easy to trick MapTool to leave yout html as it is -
you just have to break it. Replace all left brackets in the tags by the
html entity for that bracket. The result isnt valid html anymore, so
MapTool cannot format it - but it looks all the same to you. You can
even copy it and use it as valid html code.

## Example

``` mtmacro numberLines
[h: output = "<h1>This is a headline</h1><p>but <em>this</em> is not</p>"]
[h: output = replace(output, "<", "<")]
[r: output]
```

[Category:Cookbook](Category:Cookbook "wikilink")