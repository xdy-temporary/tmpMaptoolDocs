token_property|Token:token property{{\!}}token property\]\] from a
[Token:library token{{\!}}library
token](Token:library_token{{!}}library_token "wikilink"). If the lib
argument is not specified then the [Token:token property{{\!}}token
property](Token:token_property{{!}}token_property "wikilink") will be
retrieved from the [Token:library token{{\!}}library
token](Token:library_token{{!}}library_token "wikilink") that the macro
is currently running from.

Unlike , this function will not retrieve the default value of a campaign
property. Default values are generally programmed as local variables in
a macro, then overridden with the result of this function if this
function returns a value. An example is shown below.

|usage=

``` mtmacro numberLines
getLibProperty(name)
getLibProperty(name, lib)
```

**Important Note** As mentioned in the introduction, if the value of the
property on the Token equals the default value, the function will return
nothing\! This means that if e.g. you set the default property to

``` mtmacro numberLines
Weapons : Shotgun, Pistol, Revolver
```

And you leave the e.g. the value on the token lib:Compendium unchanged,
so it will also contain the value "Shotgun, Pistol, Revolver", then

``` mtmacro numberLines
[getLibProperty("Weapons", "lib:Compendium")]
```

will return nothing\!

|examples= To get the "init" [Token:token property{{\!}}token
property](Token:token_property{{!}}token_property "wikilink") from the
[Token:library token{{\!}}library
token](Token:library_token{{!}}library_token "wikilink") that a macro is
running from use.

``` mtmacro numberLines
[getLibProperty("init")]
```

To get the "init" [Token:token property{{\!}}token
property](Token:token_property{{!}}token_property "wikilink") from the
[Token:library token{{\!}}library
token](Token:library_token{{!}}library_token "wikilink") if the library
token has such a property. If not, use a default value of "default".

``` mtmacro numberLines
[result = getLibProperty("init")]
[IF(result == ""): result = "default" ]
```

To get the "init" [Token:token property{{\!}}token
property](Token:token_property{{!}}token_property "wikilink") from a
[Token:library token{{\!}}library
token](Token:library_token{{!}}library_token "wikilink") called
"lib:Attacks" use.

``` mtmacro numberLines
[getLibProperty("init", "lib:Attacks")]
```

}}

[Category:Token Library
Function](Category:Token_Library_Function "wikilink") [Category:Property
Function](Category:Property_Function "wikilink")