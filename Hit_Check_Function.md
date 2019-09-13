Checks the value of an attack result against a target's defense. If the
attack is greater than or equal to the defense, it outputs "Hit\!" or
"Miss."

function HitCheck(attackResult,targetName,TargetDefense)

``` mtmacro
Code:
[h: attackResult = arg(0)]
[h: targetName = arg(1)]
[h: targetDefense = arg(2)]

[h: defenseValue = getProperty(targetDefense,targetName)]

[r,if(attackResult >= defenseValue): "Hit!"; "Miss."]
```

Thanks to Rumble for help with this macro.

[Category:Cookbook](Category:Cookbook "wikilink")