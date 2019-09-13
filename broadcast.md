### Using the *Bag of Tricks*

Usually in a macro you would like the execution of a macro on a player's
computer those users who own the token in context. Or maybe you want to
execute a macro on ALL clients but you have to figure out who the
current 'executer' is and run the macro for that client separately as
the  is only executed on remote clients. To make this a bit easier, I've
created a couple of functions which are part of the [Bag of Tricks
(BoT)](http://forums.rptools.net/viewtopic.php?f=46&t=16066). If you
have the *BoT* installed, then the following functions are available to
you:

#### bot_execAllPlayers()

This macro executes the macro  on ALL SELECTED clients. So in contrast
of , you do not have to worry about who is executing the macro since
everyone does.

``` mtmacro
bot_execAllPlayers (macroName, arguments, [players], [output_to])
```



*Example use:*

  - Executing the macro  located at , with the parameters  and  on the
    PC of user , with the output of the result going to all connected
    systems:

<!-- end list -->

``` mtmacro numberLines
[h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), "Tim", "all")]
```


\*The same but now for all players

``` mtmacro numberLines
[h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), bot_all(), "all")]
```


The  function is another *BoT* function that returns the names of all
players that are logged in. See below for more info.

#### bot_message()

If you want to use a different message format, one is availalbe through
this functions.

  -
Broadcasts a preformatted message to all users (default). The message
consists out of a black (bg) and white (txt) header (default) and a
delimited textbox below it, containing the message. When the message is
left empty ('') only the header will be displayed. bot_message contains
the following optional parameters (only message is required):

*A couple examples of use:*

``` mtmacro numberLines
[resultMsg = bot_message('Hello world', 'Header', 'black-white', bot_all(), 'Wolf', '', 0)]
```

``` mtmacro numberLines
[bot_message("Hellow world")]
```

``` mtmacro numberLines
[bot_message("this message is shown to gm only", "GM Only", "red-yellow", bot_gm())]
```

``` mtmacro numberLines
[bot_message("this message is shown to all but gm", "The rest", "yellow-red", bot_ngm())]
```

![Image:Example_Message.jpg](Example_Message.jpg
"Image:Example_Message.jpg")

``` mtmacro numberLines
[h:bot_message(token.name+" Takes damage", "is attacked","red-white",bot_all(),"Dragon", "Eagle")]
```

![Image:Example_Message2.jpg](Example_Message2.jpg
"Image:Example_Message2.jpg")

The following functions can be used in conjunction with bot_message()
and return a JSON ARRAY (e.g. \["Frank","Jim","Suzy"\])

The 'bot_' prefixes in all these function are added as a precaution to
make sure that there are no conflicts with a framework in which you use
the *BoT*. If you however want to use these 'retrieve user' functions
but without the 'bot_' prefix you need to create your own set of user
defined functions.