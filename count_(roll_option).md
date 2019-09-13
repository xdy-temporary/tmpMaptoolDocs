### COUNT Option

**Introduced**: Version 1.3.b41

The COUNT option executes a statement for a specified number of times,
storing the number of the current iteration in a variable called
*[roll.count](Macros:Special_Variables:roll.count "wikilink")*.

#### Usage

``` mtmacro numberLines
[COUNT(num): body]
[COUNT(num, separator): body]
```

The *[roll.count](roll.count "wikilink")* variable will take on values
from  to (). The optional separator (default ) is printed between each
iteration. Some examples of other useful separators: *nothing* , *space*
 and *break* .

#### Example

``` mtmacro numberLines
[h:numHits=3]
[COUNT(numHits): Damage = Damage + 1d12]
```

This will iterate the  Damage + 1d12}} operation 3 times, separating the
result of each iteration with the default separator (a comma). An
optional second argument to  allows the setting of a different
separator.

[Category:Roll Option](Category:Roll_Option "wikilink")
[Category:Looping Roll Option](Category:Looping_Roll_Option "wikilink")