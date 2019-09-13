The variable *token.initHold* is a binary variable that indicates
whether a token in the [Initiative
Panel](Initiative:initiative_panel "wikilink") is on hold, or is part of
the normal initiative cycle. *token.initHold* can take a value of 1
(token is on hold) or 0 (token is not on hold).

## Usage

``` mtmacro numberLines
[token.initHold = value]
```

Where *value* is either 1 or 0.

## Example

``` mtmacro numberLines
[h:status=input(
    "hold|Yes,No|Put token on hold in initiative order?|RADIO|SELECT=0 ORIENT=H VALUE=STRING"
    )]
[h:abort(status)]

[h:token.initHold = if(hold=="Yes", 1, 0)]
```

Presents the following dialog using the
[input()](Macros:Functions:input "wikilink") function:

![Image:InitHold-example.jpg](InitHold-example.jpg
"Image:InitHold-example.jpg")

and, based on the user's selection, sets *token.initHold* to either 1 or
0. When this macro is executed, the token's image or line in the
[Initiative Panel](Initiative:initiative_panel "wikilink") will be
altered to reflect its new status.

## Related Pages

  - [Initiative Panel](Initiative:initiative_panel "wikilink")
  - [token.init](token.init "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")