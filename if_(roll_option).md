\- Greater than or equal to

  - }} - Less than or equal to

  - {{=}}}} - Equal to

  - }} or  - Not equal

*Logical Operators:*

  - \- And

  - {{\!}}}} - Or

*Boolean Operators:*

  -
  -
  - \- Not

It is important to note that the *Equal to* condition operator must be
two equal signs ({{=}}}}). If you are checking for a text string, place
quotes around the text.

#### \-- Known Problems

  - **Number of () levels**

The  doesn't allow more than one level of . So,

``` mtmacro numberLines
[R, if(((1))): "true";"false"]
```

will give an error.

  - **Help\! There are ' ' in the output**

Note that currently

``` mtmacro
[r,if(val == something),CODE:{Print something}]
```

will produce extraneous single quotes in the output when the condition
is false. The workaround for this is to add an empty block for the false
side:

``` mtmacro
[r,if(val == something),CODE:{Print something};{}]
```

|example= Sets the variable  to  if the variable  equals .

``` mtmacro numberLines
[h:val=12]
[h,if(val == 12): newVal=12*12]
New Value = [r: newVal]
```

Returns  144}}

Example with logical operators:

``` mtmacro numberLines
[h,if((val > 12 && val < 24) || val == 5): val=1 ; val=0]
```

These examples perform the same function. If  is not a number, make
equal .

``` mtmacro numberLines
[h, if (! isNumber(val)): val = 0)]
```

``` mtmacro numberLines
[h, if (isNumber(val) == 0): val = 0)]
```

``` mtmacro numberLines
[h, if (isNumber(val) == false): val = 0)]
```

The following will generate an error:

``` mtmacro numberLines
[h,if(getName(getSelected()) == "Giant Rat"): val=1]  --- ERROR, too many parenthesis on condition!
[h,if(getName() == "Giant Rat")): val=1] ---  This is OK.
```

|also= , , , [Introduction to Macro
Branching](Introduction_to_Macro_Branching "wikilink") }}

[Category:Branching Roll
Option](Category:Branching_Roll_Option "wikilink")