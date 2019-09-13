### FOREACH Option

**Introduced**: Version 1.3.b46

Iterates over the contents of a string list in the format . Can also be
used easily with [JSON arrays and JSON
objects](Introduction_to_JSON_Datatypes "wikilink"). [String Property
Lists](String_Property_List "wikilink") can be processed with a couple
of extra functions.

#### Usage

``` mtmacro numberLines
[FOREACH(var, list): body]
[FOREACH(var, list, output_separator): body]
[FOREACH(var, list, output_separator, list_separator): body]
```

default value is
default value is . Some examples of other useful separators: *nothing* ,
*space*  and *break* .

### Examples

#### String List Example

``` mtmacro numberLines
[h: enemyList="Orcs, Goblins, Ogres, Trolls"]
[FOREACH(enemy, enemyList, "<br>"): "You really hate " + enemy]
```

#### JSON Array Example

``` mtmacro numberLines
[h: enemyList = json.append("","Orcs, Goblins, Ogres, Trolls")]
[FOREACH (enemy, enemyList, "<br>"): "You really hate " + enemy]
```

#### JSON Object Example

(Note that using foreach with a JSON object will result in only the keys
being returned as vars).

``` mtmacro numberLines
[h: enemyList = json.set("","Orcs", "Bob, Dave", "Goblins", "Graham", "Ogres", "Philip, Emanual", "Trolls", "Ig, Og, Ug")]
[FOREACH (enemy, enemyList, "<br>"): "You really hate " + enemy]
```

All the above will output:

`You really hate Orcs`
`You really hate Goblins`
`You really hate Ogres`
`You really hate Trolls`

#### Using with \[code():\] and output_separator

To use roll options with your  loop, you will need to use  roll option.
In this example I have separated the results with the string .

``` mtmacro
[h: enemyList="Orcs; Goblins; Ogres; Trolls"]
[FOREACH(enemy, enemyList, " then ", ";"), CODE:
    {
    [r: enemy]
    }
]
```

output:

`Orcs then Goblins then Ogres then Trolls`

#### String Property List Example

``` mtmacro numberLines
[h: enemyStrProp = json.toStrProp(json.set("","Orcs", "Bob, Dave", "Goblins", "Graham", "Ogres", "Philip, Emanual", "Trolls", "Ig, Og, Ug"))]
[FOREACH(enemy, enemyStrProp, "<br>", ";"), code:
    {
    [h: enemyList = stringToList(enemy, "=")]
    [h: name = listGet(enemyList, 0)]
    [h: value = listDelete(enemyList, 0)]
    [r: "You really hate " + name + " who are " + value]
    }
]
```

output:

`You really hate Orcs who are Bob, Dave`
`You really hate Goblins who are Graham`
`You really hate Ogres who are Philip, Emanual`
`You really hate Trolls who are Ig, Og, Ug`

### See Also

, , , , ,

[Category:Roll Option](Category:Roll_Option "wikilink")
[Category:Looping Roll Option](Category:Looping_Roll_Option "wikilink")