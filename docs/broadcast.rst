.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction

   |name=broadcast
   |trusted=true
   |version=1.3b77
   |description=
   Allows sending a message directly to the chat area of another/all connected MapTool clients. It does not display the sender's name or token image in front of the message.

   It lets send you a message either to all or a list of players - use the player names or the keyword {{code|"gm"}}. As delimiter you can specify either a string list separator character or {{code|"json"}} if you specify the target list as json array. The big differences compared to a normal chat message are:

   #  if the message is part of a macro, then the message is sent even if the macro is aborted (after the broadcast),
   #  the sender of the message is NOT displayed, and
   #  if you broadcast an {{func|execLink}}, then that macro is AUTOMATICALLY executed on the clients it's broadcasted to, with the exception of the client that sends the message!
    
   |usage= 
   <source lang="mtmacro" line> broadcast(message, [targets], [delimiter]) </source>
   [[Category:Miscellaneous_Function|Category:Miscellaneous Function]]

   '''Parameters'''
   {{param|message|a message that is broadcasted to the users that are listed as parameters.}}
   {{param|targets|are the user names (so not token names) but the names of the users that are logged in. "gm" is also a valid parameter to give. E.g.: "tim, tom, tarra". Defaults to all players (so if no parameter is given the message is send to all players).}}
   {{param|delim|The delimiter used to separate the values in the String List that is given, defaults to {{code|","}}. If {{code|"json"}} is specified, a JSON array is expected instead of a String List.}}

   |examples=
    
   *Sending a message to all players:
   <source lang="mtmacro" line>
   [h: broadcast("Hello World")]
   </source><br />
   *Sending a message to all GMs only:
   <source lang="mtmacro" line>
   [h: broadcast("Hello World", "gm")]
   </source><br />
   *Sending a message to "tim" and "tom" only (default comma delimiter):
   <source lang="mtmacro" line>
   [h: broadcast("Hello World", "tim, tom")]
   </source><br />
   *Using json as the delimiter:
   <source lang="mtmacro" line>
   [h: broadcast("Hello World", '["tim", "tom"]')]
   </source> or 
   <source lang="mtmacro" line>
   [h: broadcast("Hello World", json.append("", "tim", "tom"))]
   </source><br />
   *Executing the macro {{code|update()}} located at {{code|lib:Token}}, for the token {{code|Dragon}} on the PC of user {{code|Tim}}:
   <source lang="mtmacro" line>
   [h: link = macroLinkText("update@Lib:Token", "none", "", "Dragon")]
   [h: broadcast(execLink(link), "tim")]
   </source><br />
   }}

.. _using_the_bag_of_tricks:

Using the *Bag of Tricks*
=========================

Usually in a macro you would like the execution of a macro on a player's
computer those users who own the token in context. Or maybe you want to
execute a macro on ALL clients but you have to figure out who the
current 'executer' is and run the macro for that client separately as
the is only executed on remote clients. To make this a bit easier, I've
created a couple of functions which are part of the `Bag of Tricks
(BoT) <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__. If you
have the *BoT* installed, then the following functions are available to
you:

bot_execAllPlayers()
--------------------

This macro executes the macro on ALL SELECTED clients. So in contrast of
, you do not have to worry about who is executing the macro since
everyone does.

.. code:: mtmacro

   bot_execAllPlayers (macroName, arguments, [players], [output_to])

| 
| 
| *Example use:*

-  Executing the macro located at , with the parameters and on the PC of
   user , with the output of the result going to all connected systems:

.. code:: mtmacro
   :number-lines:

   [h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), "Tim", "all")]

| 
| \*The same but now for all players

.. code:: mtmacro
   :number-lines:

   [h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), bot_all(), "all")]

| 
| The function is another *BoT* function that returns the names of all
  players that are logged in. See below for more info.

bot_message()
-------------

If you want to use a different message format, one is availalbe through
this functions.

-  

   .. raw:: mediawiki

      {{code|bot_message(0:message [, 1:headertxt, 2:color (bgcolor-txtcolor), 3:userList, 4:token, 5:target, 6:broadcast])}}

Broadcasts a preformatted message to all users (default). The message
consists out of a black (bg) and white (txt) header (default) and a
delimited textbox below it, containing the message. When the message is
left empty ('') only the header will be displayed. bot_message contains
the following optional parameters (only message is required):

*A couple examples of use:*

.. code:: mtmacro
   :number-lines:

   [resultMsg = bot_message('Hello world', 'Header', 'black-white', bot_all(), 'Wolf', '', 0)]

.. code:: mtmacro
   :number-lines:

   [bot_message("Hellow world")]

.. code:: mtmacro
   :number-lines:

   [bot_message("this message is shown to gm only", "GM Only", "red-yellow", bot_gm())]

.. code:: mtmacro
   :number-lines:

   [bot_message("this message is shown to all but gm", "The rest", "yellow-red", bot_ngm())]

.. figure:: Example_Message.jpg
   :alt: Image:Example_Message.jpg

   Image:Example_Message.jpg

.. code:: mtmacro
   :number-lines:

   [h:bot_message(token.name+" Takes damage", "is attacked","red-white",bot_all(),"Dragon", "Eagle")]

.. figure:: Example_Message2.jpg
   :alt: Image:Example_Message2.jpg

   Image:Example_Message2.jpg

| The following functions can be used in conjunction with bot_message()
  and return a JSON ARRAY (e.g. ["Frank","Jim","Suzy"])
| 

The 'bot_' prefixes in all these function are added as a precaution to
make sure that there are no conflicts with a framework in which you use
the *BoT*. If you however want to use these 'retrieve user' functions
but without the 'bot_' prefix you need to create your own set of user
defined functions.
