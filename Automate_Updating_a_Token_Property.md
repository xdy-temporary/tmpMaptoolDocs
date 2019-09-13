This section expects that you are already familiar with how to add
[macro buttons](Introduction_to_Macro_Writing "wikilink") to the MapTool
user interface. __TOC__

### Example: Updating Hit Points

Let's say you have a property to represent hit points. We'll call our
property . Now we want some easy way to update , so we're going to
create a [macro button](Macro_Button "wikilink") that executes a
[macro](Introduction_to_Macro_Writing "wikilink").

First, consider how you want this to work. We want a window to popup on
the screen and ask the user to enter a number. That number will be
subtracted from , so the user can use a positive number to represent
damage and a negative number to represent healing. (We'll show another
approach later.)

The first step will be to prompt for the number. MapTool has this
ability built-in. All we need to do is use a variable name that doesn't
exist yet and MapTool will popup the prompt\! The name of the variable
is part of the prompt, so we'll use a descriptive name. How about ?

``` mtmacro numberLines
[ damage = AmountOfDamage ]
```

Notice the extra variable name and the equals sign? That tells MapTool
to calculate whatever is on the right of the equals sign and store the
result into the variable on the left. In this case, there's no formula,
so this becomes simply a copy -- from the variable  to . But when
MapTool tries to read the value of the variable and it doesn't exist,
the popup will automatically appear\! That's perfect for what we want\!

Now the next step is to subtract that from the  property. Fortunately,
what you learned in the last paragraph can be used again:

``` mtmacro numberLines
[ damage = AmountOfDamage ]
[ HP = HP - damage ]
```

This time the second line calculates the formula on the right () and
stores the result into ... ? Isn't that going to screw up our  value?

No, it doesn't screw it up, but it does *replace* that value with the
result. And because  is a property, the result is stored back into the
token's property. If you were to right-click on the token and save it to
an external file, the new value of  is stored with it. When the token is
later reloaded, that value will come with it.

If you want to add to the hit points instead, you have two choices:
either the user can enter a negative number, or you can change the  to a
. The first option is easy because it puts the burden on the user\! The
second option is really an option -- who wants to edit their macro every
time they want to switch from damage to healing? Another choice not
listed above would be to create a second macro. Then there could be one
macro for adding damage and one for adding healing.

There's a few things still needed here to make this a little prettier,
but those are future steps. Go ahead and try this out right now on a
token that you create in MapTool. (The default property type, *Basic*,
includes a property named .) And try adding the second macro as well,
just for the practice. (Believe me, the more practice you get early in
the process, the easier it will become later on.)

### Example: Let's Rest for a Minute...

So let's say that you now have a macro button that prompts you to change
the token's hit points through damage or healing as described above. How
do we reset their hit points to their maximum when they rest?

We already know that we have a  and  properties, so when they are healed
up we simply need to copy the value in  into . That should give you what
you need to create a simple one-line macro:

``` mtmacro numberLines
[ HP = HPmax ]
```

Simple, right? But for the sake of argument, let's expand on this a bit.
Instead of restoring all of the hit points to the creature, we will
prompt the user for the number of hours that the creature will be
resting. For my demonstration, I'm assuming that there's a property
named . If it rests for less than 24 hours, it gets back  hit points. If
it rests for 24 hours or more, it gets back .

``` mtmacro numberLines
[ hours = NumberOfHours ]
[ healing = if(hours < 24, Level * 2, Level * 6) ]
[ HP = HP + healing ]
```

You may notice the  function on the second line. One word of warning
when using the  function: both the true and the false sections are
executed\! For that reason, you may want the  roll option instead. Note
that the syntax is slightly different between the two, so be careful
about which one you choose.

### Example: One Macro to Rule Them All

Okay, so let's say you want to have one macro to handle all your healing
needs. Using D\&D 4th Edition, for example, you can:

  - spend a Healing Surge and regain HP
  - spend a Healing Surge without gaining HP
  - gain HP as if you spent a Healing Surge
  - gain a set number of HP (alone or in addition to a Healing Surge)
  - gain Temporary HP (alone or in addition to a Healing Surge, and
    temporary HPs don't stack)

Using the simple variable prompt explained above becomes clumsy, so
let's use the  function instead:

``` mtmacro numberLines
[ cancel = input("SpendSurge | 1 | Spend Healing Surge? | CHECK",
                 "GainSurge | 1 | Gain Surge HP? | CHECK",
                 "ExtraHeal | 0 | Additional Healing",
                 "GainTempHP | 0 | Temporary Hit Points") ]
[ abort(cancel) ]
```

This will prompt you for all possible variations detailed above, in a
single input screen. ((image needed)) Then, you can use some  functions
or  roll options to update all the properties involved. This example
assumes that you're using the token properties , ,  and :

``` mtmacro numberLines
[ cancel = input("SpendSurge | 1 | Spend Healing Surge? | CHECK",
                 "GainSurge | 1 | Gain Surge HP? | CHECK",
                 "ExtraHeal | 0 | Additional Healing",
                 "GainTempHP | 0 | Temporary Hit Points") ]
[ abort(cancel) ]
[ if(SpendSurge): SurgeRemain = SurgeRemain - 1 ]
[ if(GainSurge): HP = HP + SurgeValue ]
[ HP = HP + ExtraHeal ]
[ TempHP = max(TempHP, GainTempHP) ]
```

Notice that the  function was used after the  function to make sure
that, in case the user clicked "Cancel" in the input window, the
properties wouldn't be updated.

[Category:How To](Category:How_To "wikilink")