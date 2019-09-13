## Introduction

This is a guide to the "advanced" macro branching option, .

## Assumptions

This assumes you have an understanding of what a roll option is, and
that you've read the preceding tutorials.

Also, don't forget to enable the *Use ToolTips for Inline Rolls* option
in MapTool Preferences.

## MACRO: Running Other Macros

One of the best practices when you write macros - especially when they
become complex - is to keep them streamlined and lean, and only have
them do what they need to do - for instance, if you have a macro that
adds a skill to a token, it doesn't need to be the same macro that
checks to see if an attack hits, or records damage taken. It just adds
skills.

Writing macros this way - each macro doing something relatively small -
is a good way to keep yourself organized and keep your macros clear (it
also makes them easier to fix if something goes wrong\!). What's more,
it helps keep your memory use lower, so you don't get run into [stack
overflow errors](Stack_Size "wikilink") or, more commonly, slow macros.

But if you do this, how can you make one macro run based on another one
- surely, you don't want to have to hit each button every time something
happens, right? Enter the  roll option.

### What's It Do?

The  roll option is they way you can have one macro - the *calling*
macro - trigger another macro, which we call the *called* macro. The
*calling* macro can send some information to the *called* macro, where
that information will be handled and processed and probably changed, and
then, if you like, the *called* macro can send some information back to
the caller.

### Why would I Use It?

Where this comes in handy is in three circumstances: first, when you
have some operation that you're always doing, but you have several
different ways that it might come up. Second, if you have a macro that
*everyone* uses. The third, and more powerful use, is when you want to
manipulate another token besides your own - then you frequently need to
use *called* macros, because there are some things only a *called* macro
can do\!

### Common Tasks from Multiple Pathways

Let's look at the first benefit: take, for example, a macro that applies
damage to a token in accordance with the [Sample
Ruleset](Sample_Ruleset "wikilink") (in other words, it looks at a
token's properties, and then deducts damage from the token's  property).
How many ways can you think a token might get damaged?

1.  It could get damaged by an attack from an enemy
2.  It could get damaged by an attack from a friend (accidental or
    otherwise)
3.  It could get damaged by falling
4.  It could be damaged by a trap

All kinds of ways. Now, suppose you have three macro to handle damage.
These macros are called **Enemy Attack**, **Friendly Fire**, and
**Environmental Damage**. Each of these causes a token's  to be reduced,
but each also has some special processing to determine *just how much*
HP reduction takes place (it's not important what the special processing
is at the moment).

So you have three macros, but each has a common element: they all in the
end reduce the token's . Consider a couple alternatives - you can:

1.  Write each macro separately, including the calculations to reduce ;
    or
2.  Write a fourth macro, containing just the calculations to reduce ,
    and have the three damage handler macros *call* that fourth to
    handle the final calculations.

The advantages of the first option are that you only need to write three
macros, and you're done. On the other hand, what if you realize you made
a mistake in your damage macro? You then have to edit it in three
places. In the second option, you only edit one copy of the damage
macro.

### Tasks Everyone Does

Building on the example above, if you have a whole bunch of macros that
everyone uses (perhaps everyone needs to have a way to attack, to
defend, and to take and heal damage), you can create a single set of
macros that everyone simply *calls*, rather than duplicating every macro
on every token, every time you need a new token on the map.

So, for example, you may want to build a "library" of macros to handle
your game (whatever game it happens to be), and then create a single set
of macros on your tokens that do nothing but *call* macros in the
library.

You'll note that it doesn't mean you have fewer macros overall - every
token still needs a set of macros to call on the library; however, it
*does* mean that your actual complex macros (the ones that took you a
long time to write) are all in one place, and you only need to alter
**one** copy in order to fix an error. If you'd copied the entire macro
set to every token, you'd have to fix *every single token* one at a time
to fix any mistakes you made.

### Manipulating Other Tokens and Trusted Macros

Generally, when a token runs a macro, or calls a macro, the macro
assumes that all properties and variables it needs to use apply to the
token *running* the macro. So if Bork the Brave calls a macro in a macro
library, that library macro is going to assume that it needs to do its
thing on Bork the Brave.

However, sometimes Bork the Brave does *not* want this - maybe Bork the
Brave just whacked a troll with his sword, and wants the damage to be
applied to the troll (and, by extension, most definitely does *not* want
the damage applied to himself\!). He's going to want a macro that will
affect the *troll's* token, not his own.

As it turns out, however, there are some things, as mentioned, that a
regular old macro on a player token simply can't do. For instance, a
macro on a player token can't go and determine what an NPC token's
properties are. It's simply not permitted to access another token. I
think you'll agree this is a good way to go - you may not want players
being able to see property values on an NPC. Furthermore, a player token
macro can't *change* values on another token. Nobody wants the players
to be able to, for instance, reduce an enemy's armor value to zero just
before making an attack.

But still, we want to be able to do *some* things to other tokens,
right? In response to that, the concept of **trusted macros** was
developed. Trusted macros are simply macros that can perform certain
functions unavailable to other macros, such as the functions that
manipulate token properties *other than* the ones on the token who
called the macro.

### How Do I Use It?

is a roll option, so, like other roll options you've seen, it is put at
the beginning of a line and ends with a colon. The essential format of
the  roll option is:

>
>
> ``` mtmacro
> [MACRO("macroName@Lib:token"): macro_arguments]
> ```

In the above example, there are several parts:

  - The opening and closing square brackets (**\[ \]**), which surround
    *all* macro commands in MapTool
  - The word "MACRO" (it does not have to be capitalized; that's done to
    keep it noticeable\!), which is just the name of this particular
    roll option
  - *macroName*: this is the name of the macro you wish to call
  - @: this is used in the same sense as in an email address - it means
    "at"
  - **Lib:token**: this is the [Library Token](Library_Token "wikilink")
    that contains the macro you wish to call. Library tokens are a
    complex subject, but you can think of them as a single token that
    holds a "library" of macros, that can be called by other tokens or
    call each other.
  - **macro_arguments**: an *argument* is a programming term for
    information that you send to a function (or in this case, a macro)
    that you want the function to *do* something to. If you had a
    function that added two numbers together, the numbers you send to it
    would be the "arguments" to that function.

So in the command above, you've said "run the macro called *macroName*
at the library token *Lib:token*, and send it *macro_arguments* to work
on." The programming jargon for what you've just done is "calling a
macro," or "creating a macro call."

The next section will have some actual examples to help you get a grasp
of using .

### Working with Arguments and Returns

In programming terms, a function is a set of commands that *receives*
arguments (described briefly above), does some processing on those
arguments, and then *returns* a value to the place from where it was
called. The macro roll option is not technically a function, but when it
is used, the process is mostly similar: it calls on another macro, sends
it arguments, and that other macro *may* - if you write the macro so
that it does - return a value to the calling macro.

When you call a macro, you can send it any variable, string, or number
as an argument (in other words, you can replace *macro_arguments* with
a variable, a string, or a number, which is sent to the called macro).
For example, let us assume the following:

  - There is a [Library Token](Library_Token "wikilink") called
    "'Lib:MT''' which has a macro called **Use Power**.
  - You have a token for Bork the Brave, which has a macro called
    **Shield Bash**. This is one of Bork's powers.
  - You want to send the name of the power to **Use Power**, which will
    run the standard procedures to resolve the use of a power.

To have Bork's macro trigger the **Use Power** macro on **Lib:MT**, you
would create a macro called "Shield Bash", which contained the following
command:

>
>
> ``` mtmacro
> [macro("Use Power@Lib:MT"): "Shield Bash"]
> ```

So, that's great. You've sent this information off to the macro **Use
Power**. But...how does **Use Power** recognize what you sent it?

#### The Special Variable *macro.args*

Whenever you create a macro call and execute it, a special variable
called  is created. This variable is visible (that is, can be accessed,
changed, or read) only by the macro being called, and it contains
whatever you substituted in for *macro_arguments*. So, in our example
above,  is equal to "Shield Bash". So, for example, in the macro **Use
Power**, you might have a line that says:

>
>
> ``` mtmacro
> [h:powerName = macro.args]
> ```

What that line says is, "in this macro, take the value of , and assign
it to the variable ." From then on out, the variable  will have the
value "Shield Bash" (if we continue our example from above). Note that
you don't *have* to do this - you can also just refer to  wherever you
need to.

The macro being called can then use this special variable  like any
other variable - it can read it, it can change it, it can add it to
something - anything you would do with a variable. You could even ignore
it\!

Of course, if you've sent information in one direction - from the caller
to the callee, so to speak - what if you need to send information the
other way (in other words, *return* a value)?

#### The Special Variable *macro.return*

In the macro that is being called, you can do a lot of processing on the
variable . You can output text to chat and update token properties,
even. But you migh also want the results of all that processing to be
sent *back* to the calling macro - maybe you use it to create *part of*
a string, and you need to send that piece back to be assembled into the
final output you want to send to chat.

In that case, you can assign whatever value you want to send back to the
variable , which will be sent back to the calling macro. Assume, then,
that the macro **Use Power** creates a variable called  that needs to be
sent *back* to Bork's macro **Shield Bash** before it finishes. To do
this, somewhere at the end of **Use Power**, you'd add this line:

>
>
> ``` mtmacro
> [h:macro.return = powerResultText]
> ```

You've said in that line that the special variable  will be equal to
whatever  is set to, and **Shield Bash** can then use the variable  for
further processing.

### Side by Side Examples

The examples below are the two macros discussed above, side by side, to
illustrate the use of macro calls and the  and  variables. Make sure to
check out the [Sample Ruleset](Sample_Ruleset "wikilink") if you're not
familiar with some of the various game terms. Also, note that these are
not *complete* macros that include all of the possible classes and
powers in the game, but a sampling to illustrate the use of .

<table>
<thead>
<tr class="header">
<th><p>Shield Bash Macro</p></th>
<th><p>Use Power Macro</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div class="sourceCode" id="cb1"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb1-1"><a href="#cb1-1"></a>&lt;!-- Call the Use Power macro --&gt;</span>
<span id="cb1-2"><a href="#cb1-2"></a></span>
<span id="cb1-3"><a href="#cb1-3"></a>[MACRO(&quot;Use Power@Lib:MT&quot;): &quot;Shield Bash&quot;]</span>
<span id="cb1-4"><a href="#cb1-4"></a></span>
<span id="cb1-5"><a href="#cb1-5"></a>&lt;!-- Receive the variable macro.return after Use Power has finished processing.--&gt;</span>
<span id="cb1-6"><a href="#cb1-6"></a></span>
<span id="cb1-7"><a href="#cb1-7"></a>[h:hitValue = macro.return]</span>
<span id="cb1-8"><a href="#cb1-8"></a></span>
<span id="cb1-9"><a href="#cb1-9"></a>&lt;!-- Use IF to check the value of hitValue, and choose an option --&gt;</span>
<span id="cb1-10"><a href="#cb1-10"></a></span>
<span id="cb1-11"><a href="#cb1-11"></a>[h,if(hitValue == 1),CODE:</span>
<span id="cb1-12"><a href="#cb1-12"></a>{</span>
<span id="cb1-13"><a href="#cb1-13"></a>  [damageRoll = floor((1d6+Strength)/2)]</span>
<span id="cb1-14"><a href="#cb1-14"></a>  [special = &quot;Roll 1d6. On a 4 or better, the foe is stunned for three rounds.&quot;]</span>
<span id="cb1-15"><a href="#cb1-15"></a>};</span>
<span id="cb1-16"><a href="#cb1-16"></a>{</span>
<span id="cb1-17"><a href="#cb1-17"></a>  [damageRoll = &quot;None&quot;]</span>
<span id="cb1-18"><a href="#cb1-18"></a>  [special = &quot;No special effect.&quot;]</span>
<span id="cb1-19"><a href="#cb1-19"></a>}]</span>
<span id="cb1-20"><a href="#cb1-20"></a></span>
<span id="cb1-21"><a href="#cb1-21"></a>&lt;!-- Display the Damage result and special effect --&gt;</span>
<span id="cb1-22"><a href="#cb1-22"></a></span>
<span id="cb1-23"><a href="#cb1-23"></a>&lt;b&gt;Damage: &lt;/b&gt; [r:damageRoll]&lt;br&gt;</span>
<span id="cb1-24"><a href="#cb1-24"></a>&lt;b&gt;Special: &lt;/b&gt; [r:special]</span></code></pre></div></td>
<td><div class="sourceCode" id="cb2"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb2-1"><a href="#cb2-1"></a>&lt;!-- Receive macro arguments --&gt;</span>
<span id="cb2-2"><a href="#cb2-2"></a>[h:powerName = macro.args]</span>
<span id="cb2-3"><a href="#cb2-3"></a></span>
<span id="cb2-4"><a href="#cb2-4"></a>&lt;!-- Do a switch to find the power&#39;s Attack Bonus --&gt;</span>
<span id="cb2-5"><a href="#cb2-5"></a>[h,switch(powerName):</span>
<span id="cb2-6"><a href="#cb2-6"></a>case &quot;Sword&quot;: attackBonus = 2;</span>
<span id="cb2-7"><a href="#cb2-7"></a>case &quot;Bow&quot;:  attackBonus = 0;</span>
<span id="cb2-8"><a href="#cb2-8"></a>case &quot;Shield Bash&quot;: attackBonus = -1;]</span>
<span id="cb2-9"><a href="#cb2-9"></a></span>
<span id="cb2-10"><a href="#cb2-10"></a>&lt;!--Make the Attack Roll--&gt;</span>
<span id="cb2-11"><a href="#cb2-11"></a></span>
<span id="cb2-12"><a href="#cb2-12"></a>[h:attackRoll = 1d20 + Strength + attackBonus]</span>
<span id="cb2-13"><a href="#cb2-13"></a></span>
<span id="cb2-14"><a href="#cb2-14"></a>&lt;!-- Check to see if the attack succeeds (a roll of 15 or higher is a hit) --&gt;</span>
<span id="cb2-15"><a href="#cb2-15"></a></span>
<span id="cb2-16"><a href="#cb2-16"></a>[h,if(attackRoll &gt;= 15),CODE:</span>
<span id="cb2-17"><a href="#cb2-17"></a>{</span>
<span id="cb2-18"><a href="#cb2-18"></a>  [successText = &quot;a success!&quot;]</span>
<span id="cb2-19"><a href="#cb2-19"></a>  [hit = 1]</span>
<span id="cb2-20"><a href="#cb2-20"></a>};</span>
<span id="cb2-21"><a href="#cb2-21"></a>{</span>
<span id="cb2-22"><a href="#cb2-22"></a>  [successText = &quot;a failure.&quot;]</span>
<span id="cb2-23"><a href="#cb2-23"></a>  [hit = 0]</span>
<span id="cb2-24"><a href="#cb2-24"></a>}]</span>
<span id="cb2-25"><a href="#cb2-25"></a></span>
<span id="cb2-26"><a href="#cb2-26"></a>&lt;!--Display the attack result and the success, and then send</span>
<span id="cb2-27"><a href="#cb2-27"></a> back the success info for final processing--&gt;</span>
<span id="cb2-28"><a href="#cb2-28"></a></span>
<span id="cb2-29"><a href="#cb2-29"></a>The [r:powerName] attack is [r:successText].&lt;br&gt;</span>
<span id="cb2-30"><a href="#cb2-30"></a>[h:macro.return=hit]</span></code></pre></div></td>
</tr>
</tbody>
</table>

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")