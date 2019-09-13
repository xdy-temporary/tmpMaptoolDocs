The variable *token.visible* controls the visibility of the token to
players during a game. The variable can take two values, 0 (not visible)
or 1 (visible to players). This is equivalent to the "Visible to
players" option on the right-click menu for tokens.

## Examples

### Getting Token Visibility

``` mtmacro numberLines
[token.visible]
```

Will return 1 if the token is currently "Visible to players," and 0 if
it is not.

### Setting Token Visibility

``` mtmacro numberLines
[token.visible = 0]
```

Will set *token.visible* to 0 - *e.g.*, making the token invisible to
players. A more useful approach might be:

``` mtmacro numberLines
[token.visible = 1 - token.visible]
```

This creates a "toggle" macro that will alternate *token.visible*
between its two possible values each time the button is clicked.

## Related Pages

[Category:Special Variable](Category:Special_Variable "wikilink")