The variable *token.halo* allows programmatic querying and setting of
the token's **Halo**, a colored border that, if set, appears around the
token. In the image below, the yellow border around the token is the
token's halo.

![Image:Token-halo.jpg](Token-halo.jpg "Image:Token-halo.jpg")

## Examples

### Getting the Token Halo Color

``` mtmacro numberLines
Halo color: [token.halo]
```

Outputs the hexadecimal value for the token halo color. In the case of
the example image above, it would output *\#ffff00*.

### Setting the Token Halo Color

``` mtmacro numberLines
[h:token.halo = "red"]
```

or

``` mtmacro numberLines
[h:token.halo = #ff0000]
```

Sets the color of the token.halo to red (or the hexadecimal value
*\#ff0000*).

### Removing the Token Halo

``` mtmacro numberLines
[h:token.halo="None"]
```

### Color Names and Standard Colors

The *token.halo* variable accepts the following named colors (if using a
named color, enclose the value in quotes):

  - Black
  - Green
  - Yellow
  - Orange
  - Red
  - Blue
  - Cyan
  - DarkGray
  - Magenta
  - Pink
  - White

The variable will also accept any hexadecimal color value. Hexadecimal
color values do not need to be enclosed in quotes.

[Category:Special Variable](Category:Special_Variable "wikilink")