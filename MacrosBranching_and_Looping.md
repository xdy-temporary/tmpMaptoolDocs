Introduction
------------

This page details the branching and looping structures in MapTool. With the exception of the block statement, these are all [roll options](Macros:Roll:types "wikilink") and should follow the general form for roll options:

``` mtmacro
[option1[,option2]: body]
```

These may be combined with other roll options (note that in some examples, they are combined with the [Hidden Roll](Macros:Roll:types#.5B_.5D_Hidden_Rolls "wikilink") option () to hide the default output of the loop or branch).

**If you wish to combine roll options in a single statement, separate the roll options with a comma, and place the colon at the end of the sequence of roll options. Note that some combinations have unpredictable results, such as using with .**

For example, if you want to combine a Hidden Roll, , and option in a single statement, you would enter the line like so:

``` mtmacro
[h,token("JoeRandom"),foreach(item, TokensItemList): "This item's name is "+item+"!"]
```

Branching
---------

### IF Option

**Introduced**: Version 1.3.b46

This is a roll option (as mentioned above), but operates similarly to the block-style .

#### Usage

``` mtmacro
[if(condition): true_body; false_body]
```

or

``` mtmacro
[if(condition): true_body]
```

Either the or will be used, depending on the value of . If the is not given but the is , then there is no output.

#### Example

``` mtmacro
[h:val=12]
[h,if(val == 12): newVal=12*12]
New Value = [r:newVal]
```

Outputs 144}}.

#### Note

For an alternate method for evaluating “if” conditions, see the function . Note that the roll option cannot be (usefully) combined with the roll option as the roll options are not guaranteed to be executed in any particular order. This means that the function is a better choice in those cases.

### SWITCH Option

**Introduced**: Version 1.3.b46

chooses among several options and executes code based on the switch expression.

-   **<span style="color: #FF0000;">Note</span>** that the is a regular expression, so metacharacters such as and will need to have backslashes in front of them if you want to match them literally.

#### Usage

``` mtmacro
[switch(expression):
case case1: body1;
case case2: body2;
default: default_body]
```

or with a code block:

``` mtmacro
[switch(expression), code:
case case1: {body1};
case case2: {body2};
default: {default_body}]
```

#### Example

``` mtmacro
[h:powerType="at-will"]
[switch(powerType):
  case "at-will": "You may use this power as much as you like";
  case "encounter": "You may only use this power once per encounter";
  case "daily": "You may only use this power once per day"
]
```

Outputs

Using a code block:

``` mtmacro
[h:powerType="at-will"]
[switch(powerType), code:
case "at-will": {
    [r:token.name]:<br>
    [r:"You may use this power as much as you like"]
  };
case "encounter": {
    [r:token.name]:<br>
    [r:"You may only use this power once per encounter"]
  };
case "daily": {
    [r:token.name]:<br>
    [r:"You may only use this power once per day"]
  };
]
```

Using regex:

``` mtmacro
[h:powerType=".*sword.*"]
[switch(powerType):
  case "flail": "one-handed weapon; two-handed does Str*2 damage";
  case "shortsword": "used for jabs, so is a puncturing weapon";
  case "longsword": "a slashing weapon"
]
```

Outputs . Notice that the first matching clause was the one that the option found.

### MACRO Option

**Introduced**: Version 1.3.b46

runs the named macro, inserting its text into chat.

#### Usage

``` mtmacro
[macro("macro_name@location"): macro_arguments]
```

The called macro sees a variable called \[\[Macros:Special_Variables:macro.args| - Greater than or equal to

-   }} - Less than or equal to

-   {{=}}}} - Equal to

-   }} - Not equal

Logical Operators:

-   - And

-   - Or

It is important to note that the *Equal* condition operator must be two equal signs. If you are checking for a text string, place quotes around the text.

Operator Precedence:

-   - Parentheses are always done first; they can be nested

-   - Logical NOT

-   - Logical AND

-   - Logical OR

<Category:Tutorial>