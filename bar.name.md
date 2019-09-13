The *bar.\[bar_name\]* variable permits the getting and setting of the
[token bar](Token:bar "wikilink") value (and the corresponding image
displayed on the token) programmatically. Token bars are one, two, or
multi-image graphical elements displayed on a token that are used
(typically) to visually indicate the status of consumable or expendable
items or character traits (such as Hit Points, Ammunition, Health, or
the like).

Bars, like [token states](Token:state "wikilink"), are configured via
the Campaign Properties dialog and are specific to the campaign in which
they exist. In the screenshot shown below, the green-on-black line
across the top of the token is a token bar.

![Image:Bar-example.jpg](Bar-example.jpg "Image:Bar-example.jpg")

## Usage

``` mtmacro numberLines
[bar.[bar_name] = value]
```

Sets the value of the token bar named *bar_name* to the desired value.
*bar_name* is set when the bar is created, and may be any name,
provided it contains no spaces or special characters except the
underscore. *Value* must be a number between 0 and 1.

## Examples

``` mtmacro numberLines
[h: HP = HP - DamageTaken]
[h: bar.Health = HP / MaxHP]
```

Sets the value of *bar.Health* to the result of *HP / MaxHP*.

## Notes

Two functions, [setBar()](Macros:Functions:setBar "wikilink") and
[getBar()](Macros:Functions:getBar "wikilink") also exist to get and set
the value of the token bar.

## Related Pages

  - [List of Special
    Variables](Macros:Variables:list_of_special_variables "wikilink")
  - [Token Bar
    Functions](Macros:Functions:list_of_functions_by_area#Token_Bars "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")