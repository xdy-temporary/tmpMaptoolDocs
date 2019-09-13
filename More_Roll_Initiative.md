## Roll Initiative with Hold

This example contains three different macros. Together, they will roll
initiative for a group of tokens selected using a somewhat popular game
system's rules. Specifically, the rules are:

  - each token gets a card
  - tokens that are on hold do not get a card, but use their card from
    the previous turn
  - groups of monsters all use the same roll -- or as implemented,
    tokens with the same image share the same roll.
  - tokens that are dead or incapacitated (defined by having one of
    those states) do not get a card.

The code needs to be in three different macros because it nests more
than two levels of CODE. The "onCampaignLoad" macro is used to set up
some user defined function names. The main function can be called from
the chat interface with the command "\[dealinit()\]", and the macro
called by dealinit() then calls another macro. All of these macros
should be defined in the same library token.

### Macro "onCommandLoad"

``` mtmacro
[h: defineFunction("dealinit","Roll_Init@this")]
[h: defineFunction("coreinit","roll_init_core@this")]
```

### Macro "Roll_Init"

``` mtmacro
[h: initList = "booga=-1"];
[h: cardList = "-1"];
[h: rndnum = getInitiativeRound()]
[h: cntSize = initiativeSize()]
[h: setCurrentInitiative(cntSize + 1)]

[h,foreach(Selected, getSelected("json")), CODE:
{
    [h: switchToken(Selected)]
    [h: init = getInitiative()]

    [h, if(getInitiativeHold() != 1), CODE:
    {
        [h: removeFromInitiative(init)]
        [h: SelectedGMName = getTokenImage()]

        [h: init = coreinit(SelectedGMName, cardList, initList)]

        [h: arr = json.fromStrProp(initList)]
        [h, if(json.contains(arr, SelectedGMName) == 0): initList = concat(initList, ";", SelectedGMName, "=", init)]
        [h: switchToken(Selected)]
        [h: addToInitiative()]
        [h: setInitiative(init)]
    };
    {
        [h: removeFromInitiative(init)]
        [h: switchToken(Selected)]
        [h: addToInitiative()]
        [h: setInitiative(init)]
        [h: setInitiativeHold(1)]
    };]

    [h,if(getState("Dead") || getState("Incapacitated")), CODE:
    {
        [h: removeFromInitiative(init)]
    };
    {
        [h: cardList = concat(cardList,  ";", init)]
    };]
}]

[h: sortInitiative()]
[h: setCurrentInitiative(0)]

[h: setInitiativeRound(rndnum + 1)]
[h:abort(0)]
```

cardList is used to keep track of the cards that have been dealt.

initList keeps track of tokens with the same image. Tokens that are on
hold are never put in the initList, and keep their old status.

### Macro "roll_init_core"

``` mtmacro
[h: SelectedGMName = arg(0)]
[h: cardList = arg(1)]
[h: initList = arg(2)]

[h: arr = json.fromStrProp(initList)]
[h, if(json.contains(arr, SelectedGMName) != 0), CODE:
{
    [h: init = json.get(arr, SelectedGMName)]
};
{
    [h: init = 1d54]
    [h: foo = json.fromStrProp(cardList)]
    [h, while(json.contains(foo, init) != 0), CODE:
    {
        [h: init =1d54]
    }]
};]

[h: macro.return = init]
```

This macro draws a unique card from a deck of 54 cards. There's likely a
better way to implement drawing from a deck, but this is simple and
works fast enough.

### Commentary

The result is that if you have a party of 4 PCs all with different token
images, and a group of 4 skeletons with the same token image, and 2
zombies with the same token image, which would be typical, and you
select all the tokens and run this macro, your initiative list will be
populated with all the tokens. The 4 skeletons will all have the same
initiative result. The 2 zombies will both have the same initiative
result. If any of the tokens are on hold, they'll keep their last
initiative, but other tokens with the same image will share a different
initiative.

This code was based on the [Roll Initiative](Roll_Initiative "wikilink")
sample.

[Category:Cookbook](Category:Cookbook "wikilink")