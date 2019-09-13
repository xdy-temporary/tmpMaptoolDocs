token|Token:token{{\!}}token\]\] is on
[Initiative:hold{{\!}}hold](Initiative:hold{{!}}hold "wikilink") in the
[Initiative:initiative panel{{\!}}initiative
panel](Initiative:initiative_panel{{!}}initiative_panel "wikilink") or
not. This function will return 1 if the
[Token:token{{\!}}token](Token:token{{!}}token "wikilink") is on
[Initiative:hold{{\!}}hold](Initiative:hold{{!}}hold "wikilink") or 0 if
it is not.

|usage=

``` mtmacro numberLines
getInitiativeHold()
```

|examples=

``` mtmacro numberLines
[r: if(getInitiativeHold(), "You are on hold", "You are not on hold")]
```

}}

[Category:Initiative Function](Category:Initiative_Function "wikilink")