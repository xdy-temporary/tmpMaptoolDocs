JSON Objects can contain an arbitrary number of keys and values (for
which the value may itself be another JSON object). For example, a
nested JSON object called "Monsters" might look like this:

``` mtmacro numberLines
{
 "Troll":
  {
    "name":"Troll",
    "HD":4,
    "HP":75
  },
 "Orc":
  {
    "name":"Orc",
    "HD":3,
    "HP":22
  }
}
```

Note that each value in the key-value pairs in the above object is
actually a complete JSON object in its own right.

It is occasionally useful to be able to sort a JSON object that contains
*other* JSON objects based on a value in one of the "sub-objects." For
instance, if a JSON object exists that contains token names and
distances to those tokens from a given point, one may want to sort the
JSON so that the nearest objects are first, and the farthest are last.

Or, using the above "Monsters" example, one may wish to sort it by
**name**, or by **HP**, or by **HD**.

The following macro routine is a generic method to sort JSON objects
based on an arbitrary value within a nested object.

## Assumptions

  - This macro requires the use of a JSON object supporting version of
    MapTool; it was written and tested in version 1.3.b53.
  - The macro is generic, and will run using any given JSON object
    conforming to the general "nested object" structure. In this case, a
    nested JSON object is created in the beginning so that there is a
    sample object to sort. **However**: this routine should be
    applicable to JSON arrays of objects as well - it would simply
    require using the index of the nested object rather than the nested
    object's key.
  - It can be unclear which object is being discussed when you have
    multiply nested objects. In the following explanation, "nested
    object" will always refer to an object contained *within a larger
    JSON*. So, the larger object is **Monsters**, while **Troll** would
    be a *nested object.*

## Macro Code and Discussion

Please see the [full macro
code](Tutorials:Macros:JSONSortingFullCode "wikilink") for the complete
macro.

### Create Sample Object

This sequence simply creates a sample object to practice sorting. In
actual use, you may wish to pass an object as an argument, or pull an
object from a token's properties, as necessary.

``` mtmacro numberLines
[h:troll = json.set("{}", "name", "Troll", "HD", 4, "HP", 75)]
[h:orc = json.set("{}", "name", "Orc", "HD", 3, "HP", 13)]
[h:goblin = json.set("{}", "name", "Goblin", "HD", 2, "HP", 6)]
[h:gnoll = json.set("{}", "name", "Gnoll", "HD", 3, "HP", 19)]
[h:kobold=json.set("{}", "name", "Kobold", "HD", 1, "HP", 4)]
[h:monsters = json.set("{}", "Troll", troll, "Orc", orc, "Goblin", goblin, "Gnoll", gnoll, "Kobold", kobold)]
```

### Request Sorting Key and Sort Direction from User

This section is also optional (and not useful if this macro will be used
as a function/called macro), but for the example code it makes it easier
to experiment with. This section uses [input()](input "wikilink") to
gather user input, and [abort()](abort "wikilink") to halt processing if
the user hits "Cancel." Finally, it uses an
[IF():](Macros:Branching_and_Looping#IF_Option "wikilink") roll option
to set a variable with a "friendly" indicator of sort direction, which
will be used at the end in the final output.

``` mtmacro numberLines
[h:status = input(
"whichKey|name,HD,HP|Pick Sorting Key|LIST|SELECT=0 VALUE=STRING",
"whichDirection|A+,A-,N+,N-|Direction (A+/- for strings, N+/- for numbers!)|LIST|SELECT=0 VALUE=STRING"
)]
[h:abort(status)]

[h,if(substring(whichDirection,1)=="+"): dirString = "ascending"; dirString = "descending"]
```

### Set Basic Variables

This segment initializes some variables that will be used later:

  - *sortObj* is the object to be sorted (in this case, the JSON Object
    **Monsters**)
  - *sortOn* is the value on which to sort (**name**, **HD**, or **HP**)
  - *sortDirection* is the direction of the sort, which will be passed
    to [listSort()](listSort "wikilink")
  - *sortObjContentList* is a list - created using
    [json.fields()](json.fields "wikilink") - of each nested object
    within **Monsters**; effectively it is a list of the "names" of each
    monster
  - *keyList* is a list that will contain the value that corresponds to
    the thing we're sorting on - so if you choose to sort by **name**,
    then *keyList* will ultimately contain the value of **name** for
    each monster in the **Monsters** object
  - *sortedJSON* will hold the new, nicely sorted JSON object; the
    original object will be unchanged.

<!-- end list -->

``` mtmacro numberLines
[h:sortObj=monsters]
[h:sortKey = whichKey]
[h:sortDirection = whichDirection]
[h:sortObjContentList = json.fields(sortObj)]
[h:keyList = ""]
[h:sortedJSON = "{}"]
```

### Extract the Value of *sortKey* from each Nested Object

Here, we use FOREACH() to loop through each element in
*sortObjContentList* (in other words, go one-by-one through the list of
monster names). The FOREACH() option lets us say that *item* holds the
value of each of those (so for the first pass, *item* holds the first
monster name in the list, and on the second pass, it moves to the next,
and so on). We need to do this so that we can extract the detailed
information about each monsters from the **Monsters** object (in this
case, we assign the detailed information to a new variable called
*itemDetail*).

With the nested objects extracted, we can then retrieve the value of the
thing we're sorting on by using [json.get()](json.get "wikilink") on the
variable *itemDetail*. We stick that value in the previously empty list
*keyList*.

Finally, once we've gone through each nested object held within
**Monsters** and each nested object's value for our chosen sort
(remember, we put that information in the variable *sortKey*) has been
added to *keyList*, we're finished with the loop.

Now we actually can determine what the right order will ultimately be -
we sort *keyList* using [listSort()](listSort "wikilink") based on the
direction specified by the user. **This is a critical step\!** We've
gone through each object, and figured out what the *value* of the thing
we're sorting on is - so if we're sorting on "name", we've gone and
actually retrieved each object's *name*, and put it in a list with the
others. We then sort that list, which tells us the final order to use
when we reassemble the main object\!

``` mtmacro numberLines
[h,foreach(item, sortObjContentList),CODE:
{
   [h:itemDetail = json.get(sortObj,item)]
   [h: keyList = listAppend(keyList, json.get(itemDetail, sortKey))]
}]

[h:keyList = listSort(keyList, sortDirection)]
```

### Iterating through *keyList* and Each Nested Object

This is the most complex part of the routine.
[FOREACH():](Macros:Branching_and_Looping#FOREACH_Option "wikilink")
through each element in the variable *keyList* (which, you will recall,
contains the values corresponding to *sortKey* for each nested object).
For *each* element in *keyList*, we then loop through *all* of the
nested objects in **Monsters** to see which one(s) match up to the
current element of *keyList*.

So, for example, if the current value - *key* - in the outer loop is 4,
and we are sorting by "HD", the inner loop will iterate through each
nested object and check to see if the value of "HD" for that nested
object is equal to 4.

If a match is found, the matching nested object is added to *sortedJSON*
using [json.set()](json.set "wikilink"). In this fashion, we're using
*keyList* to tell us what order the final nested objects should be in,
and we then just need to go through our nested objects, setting them in
that order via the following code.

``` mtmacro numberLines
[h,foreach(key,keyList),CODE:
{
   [foreach(object,sortObj),CODE:
   {
     [objectDetail = json.get(sortObj,object)]
     [h:sortOnValue = json.get(objectDetail, sortKey)]
     [if(sortOnValue == key): sortedJSON=json.set(sortedJSON, object, objectDetail);""]
   }]
}]
```

### Outputting the Results in an Attractive Fashion

The final step is to output results. The use of
[json.indent()](json.indent "wikilink") here simply makes the sorted
JSON object easy to read.

``` mtmacro numberLines
JSON Object sorted by [r:whichKey], [r:dirString]:<br>
<pre>[r:json.indent(sortedJSON, 3)]</pre>
```

[Category:How To](Category:How_To "wikilink")