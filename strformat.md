because an integer was provided where a float was expected and it's
telling you that the  type doesn't apply to integers. A similar message
is displayed if you try to display a floating point value as a decimal.)

``` mtmacro numberLines
    [strformat("%f", -10.502)] [strformat("%g", -10.502)]
    [strformat("%+e", -10.502)] [strformat("%5.1f", -10.502)]
    [strformat("%(5.1f", -10.502)]
```

Returns:

`   -10.502000 `
`   -10.5020 `
`    -1.050200e+01 `
`   -10.5 `
`   (10.5)`

}}

[Category:String Function](Category:String_Function "wikilink")