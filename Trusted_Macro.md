A Trusted Macro is a macro that fits certain criteria, allowing it
access to [functions](:Category:Macro_Function "wikilink") and [roll
options](:Category:Roll_Option "wikilink") that are protected from
normal use.

[Functions](:Category:Macro_Function "wikilink") and [roll
options](:Category:Roll_Option "wikilink") that require a Trusted Macro
will have the following note on their article:  Some parameters are only
usable within a Trusted Macro, they will have the following note on
their description:

In order for a macro to be trusted it must adhere to three requirements.
**If a macro is typed into the chat window, and not attached to a macro
button, the only requirement is that the GM is the person who typed the
macro.**

### First Requirement

A trusted macro must not be editable by players. Allowing players to
edit trusted macros is tantamount to making all of their macros trusted.
To make it so players cannot edit a macro, you must uncheck the Allow
Players to Edit Macro checkbox on the Options tab of the macro window.
This setting defaults to being checked, allowing players access to edit
any macro. As of 1.3b54 the default can be changed in the Preferences.

![trustedMacro1.jpg](trustedMacro1.jpg "trustedMacro1.jpg")

### Second Requirement

A trusted macro must not call another macro that is not trusted, any
such call will cause the originating macro be considered an untrusted
macro.

### Third Requirement

After satisfying the first and second requirements, the third
requirement can be satisfied in two ways:

  - Clicking the macro button as a GM.
  - Placing the macro on a [library token](Library_Token "wikilink") and
    having a player call it using a [roll
    option](:Category:Roll_Option "wikilink") or [macro
    link](macroLink "wikilink").

### Why trusted macros?

Using trusted macros can, for example, allow gamemasters to set up
macros on [library tokens](Library_Token "wikilink") that can be called
by players, but edited only by GMs, and which can access functions that
players would not normally be able to access. Such macros can use
trusted-only options or functions (such as the
[\[token():](token_\(roll_option\) "wikilink")\] roll option or the
[switchToken()](switchToken "wikilink") function) to modify or read
values from NPC tokens that players do not own.

## A macro is trusted when ...

` * Anything the GM types into the input box is trusted`

` * Anything a non GM types into the input box is not trusted.`

` * Any auto execute macro that is non player editable is trusted.`

` * Any auto execute macro that is player editable is not trusted.`

` * Any non auto execute macro gets copied into the input box to be edited, so results in one of the first two rules`

*quoted
Craig([1](http://forums.rptools.net/memberlist.php?mode=viewprofile&u=1338))*

Lets test macros under certain combinations of macro location, player or
gm, auto-execution and if it is player-editable or not. The test was
performed using  and the campaign macro was "applied to token".

| Macro location | clicked by | auto-execute | player-editable | is trusted               |
| -------------- | ---------- | ------------ | --------------- | ------------------------ |
| campaign       | GM         | •            | •               | ✓                        |
| campaign       | GM         | •            | \-              | ✓                        |
| campaign       | GM         | \-           | •               | ✓                        |
| campaign       | GM         | \-           | \-              | ✓                        |
| lib:token      | GM         | •            | •               | \- |- bgcolor= lightgrey |
| pc token       | GM         | •            | •               | \-                       |
| pc token       | GM         | •            | \-              | ✓                        |
| pc token       | GM         | \-           | •               | ✓                        |
| pc token       | GM         | \-           | \-              | ✓ |- bgcolor= lightgrey  |
| pc token       | player     | •            | •               | \-                       |
| pc token       | player     | •            | \-              | ✓                        |
| pc token       | player     | \-           | •               | \-                       |
| pc token       | player     | \-           | \-              | \-                       |

*\*: This is actually not editable by the player since its a campaign
macro.*

[Category:Macro](Category:Macro "wikilink")