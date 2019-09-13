string_list|String List{{\!}}string list\]\] is returned with the
default value of  is used.

  - If the delimiter  then a [json array](JSON_Array "wikilink") is
    returned.
  - Otherwise a [string list](Macros:string_list "wikilink") is returned
    with the delimiter passed in.

 

|usage=

``` mtmacro numberLines
getNPC()
getNPC(delim)
```

delim is the delimiter used to separate the values in the [string
list](Macros:string_list "wikilink") which defaults to  if not
specified.

|example= To display the ids of all of the [NPC
tokens](Token:NPC_token "wikilink") on the current
[map](Map:map "wikilink") use.

``` mtmacro numberLines
[h: ids = getNPC()]
[foreach(id, ids, "<br>"): id]
```

|changes=

  - **1.3b49** - Added  delimiter option.

|also=  }}

[Category:Find Function](Category:Find_Function "wikilink")