The variable *token.label* allows programmatic querying and setting of
the token's [Label](Token:Token_label "wikilink") (the third text field
in the screenshot of the Edit Token dialog).

![Image:Edittoken-name-and-label.jpg](Edittoken-name-and-label.jpg
"Image:Edittoken-name-and-label.jpg")

## Examples

### Getting the Token Label

``` mtmacro numberLines
Token Name: [token.label]
```

Outputs the value of *token.label*.

### Setting the Token Label

``` mtmacro numberLines
[h:token.label = "Random Passerby"]
```

Sets the value of *token.label* to "Random Passerby".

## Related Pages

  - [token.gm_name](token.gm_name "wikilink")
  - [token.name](token.name "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")