.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Chat Commands}}

MapTool's chat system supports a number of "slash commands" (that is,
commands preceded by a "/" character) that execute particular actions
when typed directly into chat.

.. _general_usage:

General Usage
=============

To use a chat command, you type directly into the chat window, using the
following format:

.. code:: mtmacro
   :number-lines:

   /command argument

where *command* is one of the commands in the table below, and
*argument* is an appropriate argument (a dice roll, or a string of text,
etc.) upon which the command acts.

**NOTE**: Remember, the commands shown below are always preceded by a
forward slash (**/**) character.

**NOTE**: Slash commands will only work correctly in a MapTool macro if
they are the first text in the macro. This is a result of macros simply
being text that is "stored up" until it's pushed into the chat window
where it's executed. However, many chat commands have related macro
functions that can achieve the same effect within only a part of a chat
message. Those functions are pointed out below where applicable.

.. _built_in_commands:

Built-in Commands
=================

================ ======================= ===========================================================================================================================
Command          Built-in Alias (if any) Description
================ ======================= ===========================================================================================================================
addtokenstate    tsa                     Add a new token state that can be set on tokens
alias            alias                   Create a command alias
clear            clr                     Clear the chat window
clearaliases                             Clear all aliases
color            cc                      Change your chat text color. Color must be in hexadecimal format, e.g. */cc #ff0099*
emit             e                       Broadcast text to all connected players without revealing who sent it (GM-only command)
emote            me                      Broadcast an emote to all connected players
gm               togm                    Send text to GM exclusively (see )
goto             g                       Go to location or go to token, e.g. */goto X,Y* or */goto tokenname* (see )
help             h                       Display a list of available commands
impersonate      im                      Speak as if you were someone or something else (typically, speak as if you were a token)
loadaliases                              Load a file that contains aliases, one per line, with a : between the name and the value (just as if you were typing it in)
loadtokenstates  tsl                     Load all of the token states to a file
ooc                                      Out-of-character chat (chat is enclosed in double parentheses)
reply            rep                     Reply to the last player to whisper to you
roll             r                       Roll dice (using a `Dice Expression <Chat:Dice>`__) and broadcast result to all players (see )
rollgm           rgm                     Roll dice and broadcast result only to yourself and the GM
rollme           rme                     Roll dice and show the result only to yourself
rollsecret       rsec                    Roll dice and show the result only to the GM (hiding the result from even yourself)
savealiases                              Save all current aliases to a file
savetokenstates  tss                     Save the current set of token states to a file
say              s                       Broadcast a message to all connected players
self                                     Send a message only to yourself (see )
settokenproperty stp                     Set the value of a `Token Property <Token:token_property>`__ (see )
settokenstate    sts                     Set the value of a `Token State <Token:state>`__ (see )
table            tbl                     Run a table lookup, e.g. */tbl tablename value-to-lookup* (see )
tmacro           tm                      Run the given macro on the selected token (see )
tsay             ts                      Say the given speech on the selected token (see )
whisper          w                       Send a message to a specific player (see )
================ ======================= ===========================================================================================================================

`Category:MapTool <Category:MapTool>`__
