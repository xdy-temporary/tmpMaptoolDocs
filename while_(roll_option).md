### WHILE Option

**Introduced**: Version 1.3.b46

Repeatedly executes a statement until a condition becomes false.
The default **separator** is . Some examples of other useful separators:
*nothing* , *space*  and *break* .

#### Usage

``` mtmacro numberLines
[WHILE(condition): body]
[WHILE(condition, separator): body]
```

#### Example

``` mtmacro numberLines
[h:num = 10]
[WHILE(num >= 0): num = num - 1]
```

Outputs *9,8,7,6,5,4,3,2,1*

#### Example

This example demonstrates how to put multiple instructions inside a
loop using the  block extension.

Note the use of the second parameter to  to force a line break in the
HTML output. Also notice that putting text on separate lines does NOT
force the output on separate lines; the HTML  element is needed for
that.

``` mtmacro numberLines
[h: End = 5]
[H: Num = 0]
[WHILE(Num < End, "<br>"), CODE: {
    Number is [Num = Num + 1],
    Next will be [Num+1]
}]
```

Outputs:

[Category:Roll Option](Category:Roll_Option "wikilink")
[Category:Looping Roll Option](Category:Looping_Roll_Option "wikilink")