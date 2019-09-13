## Roll Initiative

This is a rather complex macro that will roll initiative for a group of
tokens selected using a popular game system's rules. Specifically, the
rules are:

  - each token rolls 1d20 and adds a bonus (stored in the Initiative
    Property).
  - ties go to the token with the higher bonus.
  - groups of monsters all use the same roll -- or as implemented,
    tokens with the same image share the same roll.

The code for this is below:

``` mtmacro numberLines
[h: initList = "booga=-1"];

[h, foreach(Selected, getSelected("json")), CODE:
{
    [switchToken(Selected)]
    [SelectedGMName = getTokenImage()]
    [arr = json.fromStrProp(initList)]
    [if(json.contains(arr, SelectedGMName) != 0), CODE:
    {
        [init = json.get(arr, SelectedGMName)]
    };
    {
        [result = 1d20]
        [init = result + getProperty("Initiative", Selected)]
        [tie = getProperty("Initiative", Selected) / 100]
        [init = init + tie]
        [initList = concat(initList, ";", SelectedGMName, "=", init)]
    }]

    [switchToken(Selected)]
    [addToInitiative()]
    [setInitiative(init)]
}]

[h: sortInitiative()]

[h,foreach(Selected, getSelected("json")), CODE:
{
    [switchToken(Selected)]
    [init = getInitiative()]
    [init = floor(init)]
    [setInitiative(init)]
}]
```

The result is that if you have a party of 4 PCs all with different token
images, and a group of 4 skeletons with the same token image, and 2
zombies with the same token image, which would be typical, and you
select all the tokens and run this macro, your initiative list will be
populated with all the tokens. The 4 skeletons will all have the same
initiative result. The 2 zombies will both have the same initiative
result. If there are any ties, tokens with the higher initiative bonus
will be presented first.

[Category:Cookbook](Category:Cookbook "wikilink")