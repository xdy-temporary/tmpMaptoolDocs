The special variable *roll.count* holds the current iteration of current
loop. It may be used with the following roll options for looping:

  - [COUNT():](Macros:Branching_and_Looping#COUNT_Option "wikilink")
  - [FOR():](Macros:Branching_and_Looping#FOR_Option "wikilink")
  - [FOREACH():](Macros:Branching_and_Looping#FOREACH_Option "wikilink")
  - [WHILE():](Macros:Branching_and_Looping#WHILE_Option "wikilink")

The *roll.count* begins at 0.

## Examples

**Simple Count**

``` mtmacro numberLines
[COUNT(5, "<br>"): "This is roll " + roll.count]
```

*Outputs:*

`This is roll 0`
`This is roll 1`
`This is roll 2`
`This is roll 3`
`This is roll 4`

**Inner and Outer Loop**

``` mtmacro numberLines
[r,foreach(item,"a,b,c,d,e,f",""),code: {
    Loop: [r: roll.count] - [r: item] -
    [r,count(6): roll.count]<br>
}]
```

*Outputs:*

` Loop: 0 - a - 0, 1, 2, 3, 4, 5 `
` Loop: 1 - b - 0, 1, 2, 3, 4, 5 `
` Loop: 2 - c - 0, 1, 2, 3, 4, 5 `
` Loop: 3 - d - 0, 1, 2, 3, 4, 5 `
` Loop: 4 - e - 0, 1, 2, 3, 4, 5 `
` Loop: 5 - f - 0, 1, 2, 3, 4, 5 `

## Related Pages

  - [Branching and Looping
    Options](Macros:Branching_and_Looping "wikilink")

[Category:Special Variable](Category:Special_Variable "wikilink")