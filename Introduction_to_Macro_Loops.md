Introduction
------------

We've looked at [branching](Introduction_to_Macro_Branching "wikilink") in macros, using , , and the more advanced roll options and . Branching is one of the most important tools for macro writing, since it lets you automate decisions based on certain factors or conditions that arise during play.

Another common task in MapTool macros is to repeat a process multiple times - for example, you may want to repeat an attack roll several times, against multiple targets (for instance, if you threw a grenade, you might need to roll to see which targets are hit by the blast), or you may want to go through a list of skills, and print out the skill rating for each one. In both cases, you're repeating the same operation several times in a row, generating different results each time. In macro writing, we call this process *looping* (you may see it described in places as “looping through a list” or “iterating over an array” - regardless, the processes to do it are *loops*).

There are four loop structures in MapTool macros: , , , and . Each of the three is a *roll option*, which means - as we've seen before:

1.  It is placed at the beginning of a macro command
2.  It is followed by a colon
    1.  If more than one roll option is used, they are separated by commas, and the *last* one is followed by a colon
3.  After the colon, you place the operation you want to do every time the loop runs

Before we continue, we'll need to introduce a couple concepts that will be used heavily in the examples below, especially for and loops.

Assumptions
-----------

I assume you've read the [Introduction to Macro Writing](Introduction_to_Macro_Writing "wikilink") and have knowledge of how to create a new macro and use some very basic commands in it (like creating a variable or a dice roll).

Also, don't forget to enable the *Use ToolTips for Inline Rolls* option in MapTool Preferences.

New Concept: String Lists and String Properties
-----------------------------------------------

RPGs have a lot of information that goes into playing them - there are stats, and skills, and dice rolls, and weapons, and equipment, and powers and magic and...well, you name it, and there's an RPG out there that covers it.

For basic things, it might make sense to create a token property for each piece of information. In fact, you can do this for every possible bit of information you want to record about a character - but already, I bet you're thinking “that's a *lot* of properties”). And it is!

Fortunately, there are other ways to store information in MapTool properties (and macro variables) that let you group information together. The two new information storing methods we'll use - which are properly referred to as *data types* - are [string lists](String_List "wikilink") and [string properties](String_Property_List "wikilink").

### String Lists

A string list is, first, a *string* - that is, a collection of alphanumeric text that is treated as just text (that is, it's not a number, so you can't add it to another number; it's not a dice roll, so MapTool won't automatically roll it; it's just a string of characters).

Second, it is a *list* - a collection of single items, separated by some sort of separating character - the (you guessed it) *separator* (also called a *delimiter*). The separator marks the beginning and end of an individual item in a list. This is a long way of saying “a string list is a single value that is a list of things, like colors: blue, green, red, orange, mauve.”

Formally - in macro code - a string list looks like:

> ``` mtmacro
> [h:listOfColors = "blue, green, red, orange, mauve"]
> ```

In the example, you'll see that we've made a variable assignment, and given the variable the values . The whole thing is enclosed in double quotes, which tells MapTool that it's a string, and from its very format, MapTool knows that it's a *string list*.

A string list can contain anything - it could be a list of names, of numbers, of dice rolls - anything you might want to keep a list of.

**However!** It is important to remember that no matter what each item in a string list *is*, it is always treated as a *string*. So if MapTool reads a string list that looks like , it will not see the first item and see a command to roll 1 six-sided die; instead it will see the character “1”, the character “d”, and the character “6”, all put together. They may look the same to us, but they don't look the same to MapTool - to turn that “1d6” into so that MapTool will roll it, we need to use the function to tell MapTool “evaluate that string *as if* it were a dice roll.” You'll see some examples of later on.

### String Properties

String properties are very similar to string lists - they are strings with special formatting, and they contain a collection of items. However, string properties have additional features that make them very useful for storing information in a different way.

The essence of a string property is the the *key - value* pairing. Basically, for each item in the string property, there is a *key* that is paired with a *value*. For instance, if you have a weapon with the following details:

-   Weapon Name: Broadsword
-   Weapon Damage Dice: 1d8
-   Weapon Damage Type: Slashing
-   Weapon Category: Versatile

You have a series of *key - value* pairs: the key “Weapon Name” is paired with the value “Broadsword,” the key “Weapon Damage Dice” is paired with the value “1d8,” and so on. A string property is simply a “formal” way to set up this kind of pairing in a single variable. The string property for the above weapon might read:

> ``` mtmacro
> [h:weapon1 = "name=Broadsword; damageDice=1d8; damageType=Slashing; category=Versatile;"]
> ```

In that string property, the word to the left of the equal sign is the *key*, and the word to the right is the *value*. The semicolon is the *separator* or *delimiter*. MapTool has special functions to retrieve and change the values within a string property, which you'll see in use later.

Now, let's get to the loops!

COUNT: Over and Over and Over and...
------------------------------------

The first looping structure we'll cover is the option. This option is the simplest loop - it repeats the operation following the colon a number of times equal to its *argument* (remember, arguments are the values or variables you put inside the parentheses). The format of a (which can also be abbreviated statement is:

> ``` mtmacro
> [count(repetitions): command]
> ```

or

> ``` mtmacro
> [c(repetitions): command]
> ```

The example should be pretty self-explanatory. It contains:

-   The option itself - without the option, we wouldn't need this tutorial, right?
-
    this is the value that tells how many times to repeat

-
    this is the actual macro command you want count to do over and over again.

Let's look at an example. Suppose you have a character who can cast a spell, which creates a cloud of poisonous gas that can hit up to nine targets at the same time. Suppose we also have a cluster of 6 hapless orcs standing in the room, that you are about to poison with this toxic cloud. The rules of your game indicate that you must roll a separate attack for each possible target, meaning that you'd have to roll your attack 6 different times. You can either do that by hand, each time, or you could write a macro that uses to roll the attack over and over, and all you need to give it is the number of times!

Here's how you'd write that macro:

> ``` mtmacro
> [h:attackBonus = 7]
>
> Toxic Cloud: [count(numAttacks): 1d20+attackBonus]
> ```

What we did here was:

-   Line 1 sets a value for , to be used later.
-   Line 3 sends the text "Toxic Cloud: " to chat, and then, begins the Count Loop. Since is *undeclared*, MapTool will prompt you for a value before it can start the loop. Once you enter that value, the count loop will process the calculation of that many times, sending the result to chat each time, and separating each result with a comma.

The output of this macro will look something like (assuming you entered 4 when prompted for ):

> Toxic Cloud: 17, 19, 12, 8

### Special Variable: *roll.count*

Since it's often useful to know what “round” or “turn” we're on when a loop is running, MapTool creates a special variable every time you start a count loop. This variable is called \[\[roll.count| happen, and display the result in chat; if is *not* greater than 0, then the loop will be halted. The output of this macro looks like:

> 9,8,7,6,5,4,3,2,1

You'll note that “10” was never shown. That's because while the loop may have started with having the value of 10, the first time we *see* any output is when the operation takes place - so the first thing we see is , which is 9.

### Example 2: The Machine-Gun

Let's look at a more complicated (and perhaps more interesting) example. In this example, we won't be using the [Sample Ruleset](Sample_Ruleset "wikilink"), mostly because I couldn't think of a useful example from that game. So, let's assume we have the following game situation:

-   A character has a machine gun with 30 rounds of ammunition
-   They may fire one to six rounds for every action
-   If their attack roll of 1d20 is greater than 15, they may make another attack; otherwise, they must end their turn. They always get at least 1 attack, though.

So what we need to do is repeat the operation until *either* the weapon runs out of ammo, or they roll less than a 15 on their attack. Here's how that macro would look:

> ``` mtmacro
> [h:ammo = 30]
> [h:hit = 1]
>
> [while(ammo > 0 && hit == 1, "<br>"),CODE:
> {
>   [h:attackRoll = 1d20]
>   [h:ammoSpent = 1d6]
>   [h,if(attackRoll > 15): hit = 1; hit = 0]
>   [h:ammo = ammo - ammoSpent]
>   Your first attack expends [r:ammoSpent] rounds, and [if(hit==1, "hits.", "misses.")] You have [r:ammo] rounds remaining.
> }]
>
> [if(hit==0): "Your turn ends because you missed a target."]
> [if(ammo==0): "Your turn ends because you are out of ammo."]
> ```

Here's the breakdown of this macro:

-   Line 1 and 2 set two important variables: and . We set to 30, per the assumptions above, and we set to 1, so that the character always gets at least *one* attack roll (if we didn't set to 1, the loop might stop before it started!).
-   Line 4 is the start of the While Loop: we establish the loop, and give it a combined condition. We say that *while* has a value greater than 30, *and* (remember, two ampersands is the logical operator “and”) *is equal to* 1, the loop should go 'round. If *either or both* of those is *not* true, then the loop should stop. Also, we set the separator to &lt;br&gt;, so that a new line will be printed each time the loop runs.
-   Lines 5 - 9 handle the actual loop processing. Note that in that loop, we make sure to set a new value for and  - this is ***critical***. If you never change the variables that your conditions are based on, then your loop will ***never stop***.

It's worth repeating: in a while loop, you ***must change the variable that your condition is checking, or you can end up with a loop that never stops***.

So, the output of this macro will look something like:

> Your attack expends 6 rounds, and hits. You have 24 rounds remaining.
> Your attack expends 2 rounds, and hits. You have 22 rounds remaining.
> Your attack expends 3 rounds, and misses. You have 19 rounds remaining. Your turn ends because you missed a target.

FOR: I Couldn't Think of Anything Catchy
----------------------------------------

The next loop structure to address is the roll option. This option is somewhat similar to , because it repeats a sequence of code a number of times based on a particular condition; it is also like because that particular condition is “has our counter reached a particular number yet?”

The general format for a loop is:

> ``` mtmacro
> [for(counter, start, end, stepsize, separator): command]
> ```

Here's how that breaks down:

-   ****: as always, we need to actually put the roll option in there
-   **counter**: this is the variable that will be used to count the iterations through the loop; typically people us a simple 1-letter variable in here, like or . For examples below, we'll use .
-   **start**: this is what the variable starts at (it can be zero, another variable, or any other numeric value)
-   **end**: this is the value that *ends* the loop
    -   In a loop where the variable is *increasing* - in other words, a loop with a positive  - the loop runs as long as is *less than*
    -   In a loop where the variable is *decreasing*- in other words, a loop with a negative  - the loop runs as long as is *greater than*
-   **stepsize**: this is how big the increment is for each iteration of the loop (for example, if you set to 2, then will increase by 2 ever iteration). The default stepsize is +1 (that is, by default, the variable increments by 1 each time the loop is processed).
-   **separator**: like with and , this is an optional separator to show between each output line from the loop; the default is a comma.

### Example 1: Basic Countdown

This example illustrates how the option's various components work. As with the previous looping structure, this is a basic countdown:

> ``` mtmacro
> [FOR(i,10,0,-2): "i is now " + i]
> ```

In this example, we have specified all components of the loop:

-   The counter variable is .
-   The start value is
-   The end value is
-   The stepsize is (the counter *decrements* by 2 every time the loop processes)

The output of this will look like:

> i is now 10, i is now 8, i is now 6, i is now 4, i is now 2

You will note that there is no *i is now 0* step - this is because when the counter counts down to 0, is no longer greater than 0.

### Example 2: Creating a Table With Multiple Rows

This example illustrates a practical use of the option to create a table that will be sent to chat, with a number of rows based on how many properties are in a String List.

> ``` mtmacro
> [h:theList = "Strength, Endurance, Dexterity, Intelligence"]
>
> [h:numberOfRows = listCount(theList)]
>
> <table border="1">
> [for(i, 0, numberOfRows, 1, ""):  "<tr><td>"+listGet(theList, i)+"</td></tr>"]
> </table>
> ```

The example above uses a few cool commands to generate the output.

-   is simply a string list variable containing four elements

-   is a function that, when you put the name of a string list variable in it, will return the number of elements in the string list

-   We create the beginning of an HTML table by using the &lt;table&gt; tag
-   The loop here uses the counter variable , which starts at 0, and counts up until it reaches . It increases by 1 each loop, and the default separator has been changed to so that no extraneous commas are printed to chat.
-   Inside the loop, we [concatenate](Introduction_to_Macro_Writing#String_Concatenation "wikilink") the HTML tags for table rows and table cells around the function . This function will retrieve, from a string list variable, the value of the element that is at the position specified in the second argument. In this case, we say, “get from the variable the value of the element that's in the same position as ” - so that it starts with element 0 (all lists start at item 0 in MapTool) and each time we loop through, it gets the next element.
-   At the end, we close the table with the appropriate HTML tag.

The output looks like this. If you add in several more elements to the variable , the table will grow in size to accommodate the new elements.

> |              |
> |--------------|
> | Strength     |
> | Endurance    |
> | Dexterity    |
> | Intelligence |
>
FOREACH: A Very Special FOR
---------------------------

The loop structure lets you repeat a set of commands a specified number of times, with flexible beginning, ending, and steps. That looping method is applicable to many things, and can be looked at as a very “general” way to loop - it gives you lots of flexibility with where you start and end, and can be used for many operations.

However, frequently loops are used to go through a list of items that is already established, and it is kind of a pain to have to make sure to count each list, then assign the variables in a loop, and make sure you can figure out how the variable corresponds to the position of an item in a list. So, a different kind of for loop - one that handles most of that without bothering *you* about it - also exists. This one is called .

In a loop, the looping structure is given two arguments: the name of a string list, and a variable. The variable takes on the value of each element in the list, in turn, as the looping structure iterates. That's a bit confusing, so first, let's look at the general structure of a loop:

> ``` mtmacro
> [foreach(item, list): command]
> ```

-   ****: once again, the roll option itself.
-   **item**: this is the variable that takes on the value of each successive element in the list or property
-   **list**: this is the string list you want the to work on
-   **command**: the operation you want performed on each successive in

To explain that in plain English: assume for a moment that there you have the names of several targets (NPC tokens) that your character wants to attack at the same time. You need to make an attack roll against each target, which is equal to 1d20 + 7, but you have to roll separately for *each* target.

You could write out the attacks each time like this:

``` mtmacro
I attack target 1: [1d20+7]<br>
I attack target 2: [1d20+7]<br>
I attack target 3: [1d20+7]<br>
I attack target 4: [1d20+7]<br>
```

And so forth and so on. Not so bad if you have 3 targets. But what if you have 6? Or 12?

So instead, what if you created a single variable that was a list of the names of each target? Then, you can use the loop to go through the list one by one and let you make the roll with a very efficient little bit of code. may be a little hard to explain, but once you understand what it can do, you will see how useful it can be!

Now, let's jump to some examples.

### Example 1: Listing the Contents of a String List

This simple example will go through a string list, and list the value of each element in the list, from beginning to end.

> ``` mtmacro
> [h:theList = "18, Bob, 29, Foo, 1009, Snorkel"]
>
> [foreach(item, theList, "<br>"): item]
> ```

In the above macro, we've created a loop that takes the list variable , and goes to each element in that list, and assigns the value of that element to the variable . We've set the separator to the HTML code for a line break, and then -- after the colon -- instructed the macro to print the value of the variable to the chat window.

The output of that macro looks like:

> 18
> Bob
> 29
> Foo
> 1009
> Snorkel

Do you see what happened there? The foreach() option went to each element in , said, “the variable is now equal to the element,” and then printed the value of to chat.

### Example 2: Attacking a Bunch of Bad Guys

Now, let's look at the example described in the beginning. Remember how we had those target names to attack? Here's how we'd do that:

> ``` mtmacro
> [h:targetList = "Orc 1, Goblin 2, Orc 4, Zombie 17, Big Boss"]
>
> [foreach(target, targetList, "<br>"),CODE:
> {
>    [h:attackRoll = 1d20+7]
>    I attack [r:target] with an attack roll of [r:attackRoll]
> }]
> ```

-   The first line simply sets up the variable , as discussed.
-   The foreach loop goes through each element in , assigning its value to the variable . So, the first time through, has the value of the first item in  - in other words, is equal to . The second time through, equals the *second* item in the list, and so on.
-   The roll option is used so we can execute multiple commands (and because it sometimes makes formatting the output a little easier)
-   Inside the CODE brackets, we calculate a variable called . This is recalculated on every loop, so it's different for each .
-   Finally, we generate some chat output, inserting the variable and the variable in the appropriate places.

The output of that macro, when sent to chat, looks like:

> I attack Orc 1 with an attack roll of 12
> I attack Goblin 2 with an attack roll of 11
> I attack Orc 4 with an attack roll of 21
> I attack Zombie 17 with an attack roll of 17
> I attack Big Boss with an attack roll of 9

Conclusion
----------

That about covers the looping basics for MapTool macros. The examples shown above are very simple, of course - just enough to show you how these work. But looping is *incredibly* useful for many applications in a MapTool macro, from generating multiple die rolls to building tables to editing token properties, so make sure to experiment with it.

<Category:MapTool> <Category:Tutorial>