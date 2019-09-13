NPC_token|NPC Token{{\!}}NPC token\]\]s on the current
[Map{{\!}}map](Map{{!}}map "wikilink"). The type of the value returned
depends on the delimiter parameter.

  - If the delimiter is not specified then a [String List{{\!}}string
    list](String_List{{!}}string_list "wikilink") is returned with the
    default value of  is used.
  - If the delimiter  then a [JSON Array](JSON_Array "wikilink") is
    returned.
  - Otherwise a [String List{{\!}}string
    list](String_List{{!}}string_list "wikilink") is returned with the
    delimiter passed in.

 

|usage=

``` mtmacro numberLines
[h: macros = getNPCNames()]
[h: macros = getNPCNames(delim)]
```

is the delimiter used to separate the values in the [String
List{{\!}}string list](String_List{{!}}string_list "wikilink") which
defaults to  if not specified.

|example= To display the names of all of the [NPC Token{{\!}}NPC
tokens](NPC_Token{{!}}NPC_token "wikilink") on the current
[Map:map{{\!}}map](Map:map{{!}}map "wikilink") use.

``` mtmacro numberLines
[h: names = getNPCNames()]
[foreach(name, names, "<br>"): name]
```

|changes=

  - **1.3b49** - Added  delimiter option.

|also=  }}

[Category:Find Function](Category:Find_Function "wikilink")