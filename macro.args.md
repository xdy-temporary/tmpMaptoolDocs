The variable *macro.args* holds the value of the argument passed to a
trusted macro via the [MACRO()](macro_\(roll_option\) "wikilink") roll
option. *macro.args* exists only within the macro that is called, and
may be manipulated like any variable in a macro.

## Examples

### 1: Single parameter

When a macro on a [library token](Token:library_token "wikilink") is
called by another macro, the calling macro may pass one argument to the
called macro:

#### Calling Macro

``` mtmacro numberLines
<!-- Call the getDamage macro -->
[h:damageDice="2d6"]
[MACRO("getDamage@Lib:test"): damageDice]
```

#### Called Macro

``` mtmacro numberLines
<!-- getDamage Macro -->
[h:damageRoll = eval(macro.args) + 9]
You hit your target for [r:damageRoll] damage!
```

In the example above, *damageDice* is the argument being passed to the
macro **getDamage**, which resides on the **Lib:test** [library
token](Token:library_token "wikilink"). Within the **getDamage** macro,
the variable  is automatically generated and assigned the value of
*damageDice*.

It's important to note that only a <u>single</u> parameter can be passed
to a macro and that parameter appears in the  variable. If more than a
single parameter needs to be sent to a macro, you may use string
property lists, a JSON array or object, or a . The first two techniques
are demonstrated below.

### 2A: Multiple parameters using String Property List

A string property list essentially bundles multiple values into a single
string which would then be split back apart inside the macro body.

#### Calling Macro

``` mtmacro numberLines
<!-- Call the doDamage macro -->
[h:damageDice="2d6"]
[h:theToken = "Bobo Fett"]
[MACRO("getDamage@Lib:test"): "Damage="+damageDice+"; Token="+theToken]
```

#### Called Macro

``` mtmacro numberLines
<!-- doDamage Macro -->
[h:dmg   = getStrProp(macro.args, "Damage")]
[h:tokid = getStrProp(macro.args, "Token")]
You hit [r: tokid] for [r:dmg] damage!
```

### 2B: Multiple parameters using JSON Array

The second way to pass multiple parameters is to use a [JSON
Array](JSON_Array "wikilink") or [JSON Object](JSON_Object "wikilink").

Using a JSON data type passes multiple values as a single unit. When
using JSON data types, there will be a single parameter coming into the
macro but because it's either an array or an object you can retrieve
individual fields quite easily.

As the  is being passed  as the first parameter in this next code block,
it's creating an empty [JSON Array](JSON_Array "wikilink") and then
appending two new values to it.

#### Calling Macro using JSON Array

``` mtmacro numberLines
<!-- Call the doDamage macro -->
[h:damageDice="2d6"]
[h:theToken = "Bobo Fett"]
[h:jsonData = json.append("[]", damageDice, theToken)]
[MACRO("getDamage@Lib:test"): jsonData]
```

#### Called Macro using JSON Array

``` mtmacro numberLines
<!-- doDamage Macro -->
[h:dmg   = json.get(macro.args, 0)]
[h:tokid = json.get(macro.args, 1)]
You hit [r: tokid] for [r:dmg] damage!
```

### 2C: Multiple parameters using JSON Object

Notice that in this next example, the  is being passed  as the first
parameter. This indicates to the function that we want a [JSON
Object](JSON_Object "wikilink").

#### Calling Macro using JSON Object

``` mtmacro numberLines
<!-- Call the doDamage macro -->
[h:damageDice="2d6"]
[h:theToken = "Bobo Fett"]
[h:jsonData = json.set("{}", "Damage", damageDice, "Token", theToken)]
[MACRO("getDamage@Lib:test"): jsonData]
```

#### Called Macro using JSON Object

``` mtmacro numberLines
<!-- doDamage Macro -->
[h:dmg   = json.get(macro.args, "Damage")]
[h:tokid = json.get(macro.args, "Token")]
You hit [r: tokid] for [r:dmg] damage!
```

## See Also

[macro.return](macro.return "wikilink"),

[Category:Special Variable](Category:Special_Variable "wikilink")