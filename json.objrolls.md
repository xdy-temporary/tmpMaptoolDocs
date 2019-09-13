</pre>

*Example:*

``` mtmacro numberLines
{json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",
        "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",
        "['3d6+1', '3d6', '3d6', '3d6-2', '3d6', '2d6']"),2)}
```

    code:{  "henchman1":   {
        "Str": 11,
        "Dex": 12,
        "Con": 13,
        "Int": 8,
        "Wis": 10,
        "Chr": 11
      },
            "henchman2":   {
        "Str": 12,
        "Dex": 11,
        "Con": 12,
        "Int": 8,
        "Wis": 12,
        "Chr": 3
      },
            "henchman3":   {
        "Str": 12,
        "Dex": 13,
        "Con": 9,
        "Int": 8,
        "Wis": 13,
        "Chr": 7
      }}

|also= [Introduction to JSON
Datatypes](Introduction_to_JSON_Datatypes "wikilink"),  }}

[Category:JSON Function](Category:JSON_Function "wikilink")