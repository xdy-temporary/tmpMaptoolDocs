''' *Requires MapTool 1.3b55* '''
The following is a user defined function that allows you to queue output
to various recipients. All of the queued output is then displayed to the
intended recipient/s after the completion of the current macro.

### Usage

``` mtmacro numberLines
outputTo(who, what)
```

**Parameters:**

### Notes

  - When sending to a specific list of recipients, the output comes
    across as a whisper; that's just the way it is.
  - Currently there is no error checking, if you want/need error
    checking, it shouldn't be hard to implement.
  - There is theoretically no limit to the amount of outputs you can
    queue, but like any software your hardware will impose its own
    limits.

### Macros

Place the following macros all on the same library token(or on different
library tokens if you know what you're doing and what to change).

<hr>

**onCampaignLoad**

``` mtmacro
[defineFunction('outputTo', 'outputTo@this')]
```

<hr>



<hr>

**outputTo**

``` mtmacro
[h: toSend = '{}']
[h: argTest = json.type(arg(0))]
[h, if(argTest=='ARRAY'), code:
{
    [h: toWho = 'list']
    [h: toSend = json.set(toSend, 'mlOutputList', arg(0))]
};{
    [h: toWho = arg(0)]
}]
[h: toSend = json.set(toSend, 'toSend', arg(1))]
[h: conditionalOutput = macroLinkText('conditionalOutput@this', toWho, toSend)]
[h: execLink(conditionalOutput, 1)]
```

<hr>



<hr>

**conditionalOutput**

``` mtmacro
[r: json.get(macro.args, 'toSend')]
```

<hr>

### See Also

[macroLinkText](macroLinkText "wikilink"),
[execLink](execLink "wikilink")

[Category:Cookbook](Category:Cookbook "wikilink")