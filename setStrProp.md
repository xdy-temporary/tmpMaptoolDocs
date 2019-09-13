1d8 ; maxdamage{{=}}8 ; value{{=}}10 ; "}}

Change the value of a key in an existing [String Property
List](String_Property_List "wikilink"):

``` mtmacro numberLines
[h: weapon = "name=longsword; damage=1d8; maxdamage=8"]
[h: weapon = setStrProp(weapon, "damage", "1d6")]
[r: weapon]
```

Returns longsword ; damage{{=}}1d6 ; maxdamage{{=}}8 ; "}}

|also=  }}

[Category:String Property List
Function](Category:String_Property_List_Function "wikilink")