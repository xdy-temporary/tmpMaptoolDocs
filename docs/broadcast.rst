======================
broadcast - MapToolDoc
======================

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

   .. rubric:: broadcast
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 broadcast() Function <#broadcast.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Using the Bag of
                  Tricks <#Using_the_Bag_of_Tricks>`__

                  -  `1.3.1
                     bot_execAllPlayers() <#bot_execAllPlayers.28.29>`__
                  -  `1.3.2 bot_message() <#bot_message.28.29>`__

         .. rubric:: broadcast() Function
            :name: broadcast-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b77**

         .. container:: template_description

            Allows sending a message directly to the chat area of
            another/all connected MapTool clients. It does not display
            the sender's name or token image in front of the message.
            It lets send you a message either to all or a list of
            players - use the player names or the keyword ``"gm"``. As
            delimiter you can specify either a string list separator
            character or ``"json"`` if you specify the target list as
            json array. The big differences compared to a normal chat
            message are:

            #. if the message is part of a macro, then the message is
               sent even if the macro is aborted (after the broadcast),
            #. the sender of the message is NOT displayed, and
            #. if you broadcast an
               `execLink() </rptools/wiki/execLink>`__, then that macro
               is AUTOMATICALLY executed on the clients it's broadcasted
               to, with the exception of the client that sends the
               message!

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                      broadcast(message, [targets], [delimiter])

         **Parameters**

         -  ``message`` - a message that is broadcasted to the users
            that are listed as parameters.
         -  ``targets`` - are the user names (so not token names) but
            the names of the users that are logged in. "gm" is also a
            valid parameter to give. E.g.: "tim, tom, tarra". Defaults
            to all players (so if no parameter is given the message is
            send to all players).
         -  ``delim`` - The delimiter used to separate the values in the
            String List that is given, defaults to ``","``. If
            ``"json"`` is specified, a JSON array is expected instead of
            a String List.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

             

            -  Sending a message to all players:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: broadcast("Hello World")]

            -  Sending a message to all GMs only:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: broadcast("Hello World", "gm")]

            -  Sending a message to "tim" and "tom" only (default comma
               delimiter):

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: broadcast("Hello World", "tim, tom")]

            -  Using json as the delimiter:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: broadcast("Hello World", '["tim", "tom"]')]

            or

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: broadcast("Hello World", json.append("", "tim", "tom"))]

            -  Executing the macro ``update()`` located at
               ``lib:Token``, for the token ``Dragon`` on the PC of user
               ``Tim``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: link = macroLinkText("update@Lib:Token", "none", "", "Dragon")]

                  #. .. code-block:: none

                        [h: broadcast(execLink(link), "tim")]

         | 

         .. rubric:: Using the Bag of Tricks
            :name: using-the-bag-of-tricks

         Usually in a macro you would like the execution of a macro on a
         player's computer those users who own the token in context. Or
         maybe you want to execute a macro on ALL clients but you have
         to figure out who the current 'executer' is and run the macro
         for that client separately as the
         `execLink() </rptools/wiki/execLink>`__ is only executed on
         remote clients. To make this a bit easier, I've created a
         couple of functions which are part of the `Bag of Tricks
         (BoT) <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__.
         If you have the *BoT* installed, then the following functions
         are available to you:

         .. rubric:: bot_execAllPlayers()
            :name: bot_execallplayers

         This macro executes the macro ``macroName`` on ALL SELECTED
         clients. So in contrast of ``broadcast(execLink())``, you do
         not have to worry about who is executing the macro since
         everyone does.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  bot_execAllPlayers (macroName, arguments, [players], [output_to])

         -  ``macroName`` - name of the macro to execute; e.g.
            ``runThisMacro@lib:token``
         -  ``arguments`` - the arguments to pass to the macro (in the
            form of a JSON array)
         -  ``players`` - a list of PLAYER names where to execute on
            (not token names). Defaults to all players
         -  ``output to`` - Send resulting output of macro to whom
            (``self``, ``gm``, ``all``, ``none``, ``gm-self``, *list*).
            Defaults to none

         | 

         *Example use:*

         -  Executing the macro ``update()`` located at ``lib:Token``,
            with the parameters ``"Hello World"`` and ``"2"`` on the PC
            of user ``Tim``, with the output of the result going to all
            connected systems:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), "Tim", "all")]

         -  The same but now for all players

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: bot_execAllPlayers("update@lib:Token", json.append("","Hello World", 2), bot_all(), "all")]

         The ``bot_all()`` function is another *BoT* function that
         returns the names of all players that are logged in. See below
         for more info.

         .. rubric:: bot_message()
            :name: bot_message

         If you want to use a different message format, one is availalbe
         through this functions.

         -  ``bot_message(0:message [, 1:headertxt, 2:color (bgcolor-txtcolor), 3:userList, 4:token, 5:target, 6:broadcast])``

         Broadcasts a preformatted message to all users (default). The
         message consists out of a black (bg) and white (txt) header
         (default) and a delimited textbox below it, containing the
         message. When the message is left empty (*) only the header
         will be displayed. bot_message contains the following optional
         parameters (only message is required):*

         -  ``message`` - The message displayed
         -  ``headerText`` - This defaults to: *. The text in the
            header, note that the 'token' parameter is set in the header
            as well on the left side. E.g. when token is 'Wolf' and
            headerTxt is 'Attacks' the header will read 'Wolf Attacks'*
         -  ``color`` - This defaults to 'black-white'. Here you can set
            the backgroundcolor-textcolor of the header. You can choose
            also to only set the backgroundcolor. Some examples: 'red',
            'black-yellow', yellow-red'.
         -  ``userlist`` - Defaults to all(). Here you can set to whom
            the message should be send. You can either fill in a user
            name yourself (NOT TOKEN NAME!) e.g. 'Frank' or you can make
            use of one of the user functions defined here below, e.g.
            all(), gm(), ownergm().
         -  ``token`` - Defaults to *. Here you can give the name of the
            token to which the message reflects. The effect is that the
            image and name of the token appears left in the header*
         -  ``target`` - Defaults to *. Here you can give the name of
            another token to which the message reflects. The effect is
            that the image of tha token appears right in the header*
         -  ``broadcast`` - Defaults to 0 the message is NOT broadcasted
            but the entire structure is returned. This is usefull is you
            want to e.g. embed the result in another message; (1)
            (default) the message is immediately broadcasted

         *A couple examples of use:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [resultMsg = bot_message('Hello world', 'Header', 'black-white', bot_all(), 'Wolf', '', 0)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [bot_message("Hellow world")]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [bot_message("this message is shown to gm only", "GM Only", "red-yellow", bot_gm())]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [bot_message("this message is shown to all but gm", "The rest", "yellow-red", bot_ngm())]

         |Example Message.jpg|

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:bot_message(token.name+" Takes damage", "is attacked","red-white",bot_all(),"Dragon", "Eagle")]

         |Example Message2.jpg|

         | 
         | The following functions can be used in conjunction with
           bot_message() and return a JSON ARRAY (e.g.
           ["Frank","Jim","Suzy"])

         -  ``bot_all()`` - all users
         -  ``bot_gm()`` - gm(s) only
         -  ``bot_ngm()`` - all but NOT gm(s)
         -  ``bot_self()`` - initiator of the macro
         -  ``bot_nself()`` - all but NOT initiator of the macro
         -  ``bot_selfgm()`` - gm(s) and initiator of the macro
         -  ``bot_nselfgm()`` - all but NOT gm(s) and initiator of the
            macro
         -  ``bot_ownergm()`` - gm(s) and owners of the currentToken. So
            NOT the token that you might give as a parameter to the
            bot_message() function but the token that is currentToken()
            at that moment.
         -  ``bot_nownergm()`` - all but NOT gm(s) and owners of the
            current token

         The 'bot_' prefixes in all these function are added as a
         precaution to make sure that there are no conflicts with a
         framework in which you use the *BoT*. If you however want to
         use these 'retrieve user' functions but without the 'bot_'
         prefix you need to create your own set of user defined
         functions.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=broadcast&oldid=7194"

