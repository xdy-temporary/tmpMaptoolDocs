The special variable  is used within the parameter of the  roll option.

### Examples

#### Example Mimicking the Default Display

``` mtmacro numberLines
[h:AtkBonus=6]
[h:AbilBonus=4]
Attack Result: [t(roll.result): 1d20+AtkBonus+AbilBonus]
```

![Tooltip-rollresult-example.jpg](Tooltip-rollresult-example.jpg
"Tooltip-rollresult-example.jpg") Evaluates , assigns that value to ,
and then displays the final result with a tooltip containing the value
of .

The parameter for the  roll option is evaluated after the roll itself is
evaluated, so that  is available for display.

#### Example of a Custom Tooltip Based on the

To illustrate how the order of evaluation can be useful, consider the
following short example:

``` mtmacro numberLines
[t( if(roll.result > 10, "Hit", "Miss") ): d20]
```

This example will display  or  depending on the result of the d20 roll,
and the tooltip when hovering over either word will be the actual
numeric result of the d20 roll.

### See Also

[Category:Special Variable](Category:Special_Variable "wikilink")