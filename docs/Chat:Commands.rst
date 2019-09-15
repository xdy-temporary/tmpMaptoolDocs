==========================
Chat Commands - MapToolDoc
==========================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Chat Commands
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `Chat:Commands </maptool/index.php?title=Chat:Commands&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/Chat_Commands/ja>`__\ 

         | 
         | MapTool's chat system supports a number of "slash commands"
           (that is, commands preceded by a "/" character) that execute
           particular actions when typed directly into chat.

         .. rubric:: General Usage
            :name: general-usage

         To use a chat command, you type directly into the chat window,
         using the following format:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     /command argument

         where *command* is one of the commands in the table below, and
         *argument* is an appropriate argument (a dice roll, or a string
         of text, etc.) upon which the command acts.

         **NOTE**: Remember, the commands shown below are always
         preceded by a forward slash (**/**) character.

         **NOTE**: Slash commands will only work correctly in a MapTool
         macro if they are the first text in the macro. This is a result
         of macros simply being text that is "stored up" until it's
         pushed into the chat window where it's executed. However, many
         chat commands have related macro functions that can achieve the
         same effect within only a part of a chat message. Those
         functions are pointed out below where applicable.

         .. rubric:: Built-in Commands
            :name: built-in-commands

         ================ ======================= ===========================================================================================================================================
         Command          Built-in Alias (if any) Description
         ================ ======================= ===========================================================================================================================================
         addtokenstate    tsa                     Add a new token state that can be set on tokens
         alias            alias                   Create a command alias
         clear            clr                     Clear the chat window
         clearaliases                             Clear all aliases
         color            cc                      Change your chat text color. Color must be in hexadecimal format, e.g. */cc #ff0099*
         emit             e                       Broadcast text to all connected players without revealing who sent it (GM-only command)
         emote            me                      Broadcast an emote to all connected players
         gm               togm                    Send text to GM exclusively (see `[g:] </rptools/wiki/g_(roll_option)>`__)
         goto             g                       Go to location or go to token, e.g. */goto X,Y* or */goto tokenname* (see `goto() </rptools/wiki/goto>`__)
         help             h                       Display a list of available commands
         impersonate      im                      Speak as if you were someone or something else (typically, speak as if you were a token)
         loadaliases                              Load a file that contains aliases, one per line, with a : between the name and the value (just as if you were typing it in)
         loadtokenstates  tsl                     Load all of the token states to a file
         ooc                                      Out-of-character chat (chat is enclosed in double parentheses)
         reply            rep                     Reply to the last player to whisper to you
         roll             r                       Roll dice (using a `Dice Expression </rptools/wiki/Chat:Dice>`__) and broadcast result to all players (see `roll() </rptools/wiki/roll>`__)
         rollgm           rgm                     Roll dice and broadcast result only to yourself and the GM
         rollme           rme                     Roll dice and show the result only to yourself
         rollsecret       rsec                    Roll dice and show the result only to the GM (hiding the result from even yourself)
         savealiases                              Save all current aliases to a file
         savetokenstates  tss                     Save the current set of token states to a file
         say              s                       Broadcast a message to all connected players
         self                                     Send a message only to yourself (see `[s:] </rptools/wiki/s_(roll_option)>`__)
         settokenproperty stp                     Set the value of a `Token Property </rptools/wiki/Token:token_property>`__ (see `setProperty() </rptools/wiki/setProperty>`__)
         settokenstate    sts                     Set the value of a `Token State </rptools/wiki/Token:state>`__ (see `setState() </rptools/wiki/setState>`__)
         table            tbl                     Run a table lookup, e.g. */tbl tablename value-to-lookup* (see `table() </rptools/wiki/table>`__)
         tmacro           tm                      Run the given macro on the selected token (see `[macro():] </rptools/wiki/macro_(roll_option)>`__)
         tsay             ts                      Say the given speech on the selected token (see `getSpeech() </rptools/wiki/getSpeech>`__)
         whisper          w                       Send a message to a specific player (see `[w():] </rptools/wiki/w_(roll_option)>`__)
         ================ ======================= ===========================================================================================================================================

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/Chat_Commands/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Chat_Commands&oldid=3999"

