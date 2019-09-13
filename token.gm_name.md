The variable *token.gm_name* allows programmatic querying and setting
of the token's [GM Name](Token:GM_Name "wikilink") (the second text
field in the screenshot of the Edit Token dialog).

*token.gm_name* is only a valid expression in a trusted macro.

![Image:Edittoken-name-and-label.jpg](Edittoken-name-and-label.jpg
"Image:Edittoken-name-and-label.jpg")

## Examples

### Getting the Token GM Name

``` mtmacro numberLines
[h:secretName=token.gm_name]
GM's Name: [secretName]
```

Outputs the value of *token.gm_name*.

### Setting the Token GM Name

``` mtmacro numberLines
[h:token.gm_name = "Soldier"]
```

Sets the value of *token.gm_name* to "Soldier."

## Related Pages

  - [token.name](token.name "wikilink")
  - [token.label](token.label "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")