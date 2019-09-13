The variable *token.name* allows programmatic querying and setting of
the token's [Name](Token:Token_name "wikilink") (the first text field in
the screenshot of the Edit Token dialog).

![Image:Edittoken-name-and-label.jpg](Edittoken-name-and-label.jpg
"Image:Edittoken-name-and-label.jpg")

## Examples

### Getting the Token Name

``` mtmacro numberLines
[h:charName=token.name]
Token Name: [charName]
```

Outputs the value of *token.name*.

### Setting the Token Name

``` mtmacro numberLines
[h:token.name = "Marok the Red"]
```

Sets the value of *token.name* to "Marok the Red."

## Related Pages

  - [token.gm_name](token.gm_name "wikilink")
  - [token.label](token.label "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")