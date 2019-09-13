Current Token
-------------

You will frequently encounter references in MapTool documentation and in the MapTool interface to the *current token.* There are actually three “categories” a token might fall into at any given time:

-   **Selected Token**: a selected token is, simply, any token that is selected on the map at a given time. If you click on a token with your mouse (and you have ownership of it), that token is *selected*, and is therefore a *selected token*.
-   **Impersonated Token**: the impersonated token is a token that you are currently speaking and acting “as” - so if you impersonate a token and enter text into chat, the token's image and name will pop up and it will appear as if that token is speaking. If you roll dice via a chat command, it will appear as if that token has rolled the dice. Impersonation is a way to take on the “role” of your character in the virtual tabletop environment.
-   **Current Token**: this is trickier, as it overlaps with the previous two categories. Simply put, the current token is the token that is *at that time* (in other words, *currently*) being changed or referred to by a [macro](Introduction_to_Macro_Writing "wikilink") command or other command in MapTool. Think of it as the “focus” of that particular macro. Because of that, it is actually possible for a token to be the selected token, the impersonated token, *and* the current token, all at the same time.

### Macros and the Current Token

The concept of the “current token” is - as you might guess - a key part of the way macros operate in MapTool.

If you select a token in MapTool, and click a macro *on that token*, the macro will by default assume that you mean “do your stuff on the token you're on!” That is, it will perform all of its operations with reference to the that token. If the macro is told to retrieve a property (for instance, to get the value of “Strength”), then it will look at the token you selected for a property called *Strength*. Likewise, if the macro is instructed to reduce “Hit Points”, it will look on the token on which it resides for a property called *Hit Points*.

On the other hand, if you click on a macro in the Campaign panel or Global panel without selecting a token on the map screen, it is possible that the macro will do nothing, or will present an error in the chat window. This is because Global and Campaign Macros do not reside on any token, and if there are any references to token properties *in* the Campaign Macro, it will have no idea what token you mean - in other words, it doesn't know what the *current token* is!

### Library Tokens and the Current Token

More advanced uses of MapTool's macro system involve the use of [Library Tokens](Library_Token "wikilink"), tokens which contain a library of macro functions that can be called by other tokens (much like a function call in other programming languages). An important thing to understand is that when a macro on a *non*-library token (a PC or NPC token, or an object) calls a macro on a Library Token, the “current token” is the *calling token*.

In other words, if a macro on the token **Grognar the Bold** calls the macro on a [Library Token](Library_Token "wikilink"), the Current Token - as far as is concerned - is **Grognar the Bold**, and all variable references, property references, and operations are performed against **Grognar the Bold**, and *not* the Library Token.

To handle operations against the Library Token itself (such as getting information from it, or setting a value for a property on the Library Token), use the [setLibProperty](setLibProperty "wikilink") and [getLibProperty](getLibProperty "wikilink") functions.

### Difference between Current and Selected/Impersonated Tokens

A *selected token* is simply a token or group of tokens that you have selected by clicking on them or dragging a selection box (or holding down SHIFT and clicking multiple tokens). The *current token* is related to selected tokens, but has some important differences.

Most of the time, it's very easy to determine which token is the current token: it's the one that is selected (for macros on the token and macros set to run on “selected tokens”) or impersonated (for Campaign and Global macros). This makes sense - the simplest way to interact with MapTool tokens is to select them and then do something with them; the assumption should be that the macro will run on the thing you have selected.

However, the current token is not *always* the selected token - it is possible to use macro commands like *[switchToken](switchToken "wikilink")* or the *[token roll option](Macros:Branching_and_Looping#TOKEN_Option "wikilink")* to change what a macro considers to be the *current token* for the purposes of retrieving or setting properties. This is a very useful feature - it lets you do things like reduce an *enemy's* hit points, or check to see if you hit an NPC token. However, it does mean that you cannot always assume the current token and the selected or impersonated token are the same.

Bottom line? In general play, the potential for differences between the current token and the selected or impersonated token are minimal. When you get into macro writing is when you'll want to pay closer attention to the differences.

### Token Naming

Due to the way MapTool is designed, it is strongly recommended that all tokens have unique names. If they do not, then macros will run into problems recognizing the *correct* current token - if you have two tokens named **Orc**, it is possible that the macro will see the wrong one, and alter its properties, when you actually meant for it to affect the *other* token named **Orc**. So, the rule of thumb is: don't use the same name for multiple tokens.

MapTool has built in “automatic number” for tokens for just this reason: it will either number them incrementally (for instance, if you copy the token **Orc 1** three times, you'll end up with three new tokens **Orc 2**, **Orc 3**, and **Orc 4**), or randomly, in which case you'd end up with something like **Orc 98**, **Orc 17**, and **Orc 35**. The numbering option can be selected in the [MapTool Preferences](MapTool_Preferences "wikilink") dialog under **Edit &gt; Preferences**.

<Category:Token>