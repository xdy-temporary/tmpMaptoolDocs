light_source|Map:light source{{\!}}light source\]\]s that are turned on
for the [Current Token](Current_Token "wikilink"). The type of the value
returned depends on the delimiter parameter.

|usage=

``` mtmacro numberLines
getLights()
getLights(type)
getLights(type, delim)
getLights(type, delim, id)
getLights(type, delim, id, mapname)
```

**Parameters**  string_list|Macros:string list{{\!}}string list\]\]. If
set to "json", a [JSON Array](JSON_Array "wikilink") is returned.
Defaults to ",".}}

|examples= To get a [Macros:string list{{\!}}string
list](Macros:string_list{{!}}string_list "wikilink") of all of the
[LightSource:light sources](LightSource:light_source "wikilink") that
the current [Token:token{{\!}}token](Token:token{{!}}token "wikilink")
has on.

``` mtmacro numberLines
[getLights()]
```

To get a [Macros:string list{{\!}}string
list](Macros:string_list{{!}}string_list "wikilink") of the
[LightSource:light sources](LightSource:light_source "wikilink") that
the current [Token:token{{\!}}token](Token:token{{!}}token "wikilink")
has on with the [LightSource:type{{\!}} lighet source
type](LightSource:type{{!}}_lighet_source_type "wikilink") of "Generic".

``` mtmacro numberLines
[getLights("Generic")]
```

|changes=

}}

[Category:Light Function](Category:Light_Function "wikilink")
[Category:Token Function](Category:Token_Function "wikilink")