### CODE

**Introduced**: Version 1.3.b46

The CODE option is used in conjunction with looping / branching options
to execute multiple statements within a single "block" of a loop or
branch, allowing the creation of more complex loops and branches.

#### Usage

``` mtmacro numberLines
[CODE: { code_block }]
```

The *code_block* is a collection of text and macro code, enclosed in a
single {} pair. Everything within the {} is treated as a single block
for the purposes of any looping or branching options.

#### Example

``` mtmacro numberLines
[h:num=5]
[WHILE(num > 0), CODE:
{
  This is iteration [r:num] <br>
  There are [r:num-1] iterations left<br>
  [num=num-1]
}]
```

Outputs

`This is iteration 5 There are 4 iterations left`
`4, This is iteration 4 There are 3 iterations left`
`3, This is iteration 3 There are 2 iterations left`
`2, This is iteration 2 There are 1 iterations left`
`1, This is iteration 1 There are 0 iterations left`
`0`

**NOTE**: the digit output at the beginning of each line is an artifact
of the WHILE loop's evaluation of *num* - since this roll does not have
the *h* option active, the result of that evaluation is displayed.

#### Nested CODE Blocks

To nest CODE:{} blocks, use a second CODE:{ } option, like so:

``` mtmacro numberLines
[h:d20roll=1d20]
[h:attackRoll=d20roll+AttackBonus]
[h,IF(attackRoll >= 16),CODE:
{
  [IF(d20roll == 20),CODE:
  {
    The attack is a critical hit!
    [h:damage=critDamage]
  };
  {
    The attack is a hit!
    [h:damage=regDamage]
  };]
};
{
  The attack misses!
};]
```

MapTool can only handle two levels of nested code.

[Category:Roll Option](Category:Roll_Option "wikilink")
[Category:Branching Roll
Option](Category:Branching_Roll_Option "wikilink") [Category:Looping
Roll Option](Category:Looping_Roll_Option "wikilink")