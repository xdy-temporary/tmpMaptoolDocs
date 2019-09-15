=================================
Guide to onTokenMove - MapToolDoc
=================================

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

   .. rubric:: Guide to onTokenMove
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

         *... and all related stuff*

         Recently a great new feature has been added to MapTool. This
         guide shall aide you to use it. Every time a token is moved (by
         the user) a specific macro is called. This macro can even
         cancel that move.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Events <#Events>`__

               -  `1.1 onTokenMove <#onTokenMove>`__
               -  `1.2 onMultipleTokensMove <#onMultipleTokensMove>`__

            -  `2 How to set it up <#How_to_set_it_up>`__

               -  `2.1 Special Variables <#Special_Variables>`__

            -  `3 Paths <#Paths>`__
            -  `4 Related Functions <#Related_Functions>`__

               -  `4.1 getLastPath() <#getLastPath.28.29>`__
               -  `4.2
                  movedOverPoints(arrayOfCoordinates) <#movedOverPoints.28arrayOfCoordinates.29>`__
               -  `4.3 movedOverToken(tokenName,
                  [lastPath]) <#movedOverToken.28tokenName.2C_.5BlastPath.5D.29>`__
               -  `4.4 getMoveCount() <#getMoveCount.28.29>`__

            -  `5 Examples <#Examples>`__

               -  `5.1 Traps/Teleporting <#Traps.2FTeleporting>`__
               -  `5.2 Movement cost
                  tracking <#Movement_cost_tracking>`__
               -  `5.3 Exposure of Fog on gridless
                  maps <#Exposure_of_Fog_on_gridless_maps>`__

         .. rubric:: Events
            :name: events

         Just like ``onCampaignLoad`` the new events are macros on a
         lib:token that have to be named like the event. Note that (and
         this is different to ``onCampaignLoad``) these events should be
         only defined on a single, unique Lib:token - doing otherwise
         can lead to unexpected behaviour. To state it clearly: there
         should not be two Lib:tokens in a campaign file with these
         macros on it at the same time.

         .. rubric:: onTokenMove
            :name: ontokenmove

         The event macro ``onTokenMove`` is called whenever any token on
         the TOKEN layer is moved via the user interface. So the event
         is NOT triggered for movement on the hidden,object or
         background layer. That tokens path is available as content of
         ``macro.args``. The moved token is the token in context, so you
         can get its id with
         `currentToken() </rptools/wiki/currentToken>`__.

         .. rubric:: onMultipleTokensMove
            :name: onmultipletokensmove

         The event macro ``onMultipleTokensMove`` is **only** called
         when more than one tokens are moved at once. The ``macro.args``
         contain a json array with all moved tokens ids. The is no token
         context.

         Note that, before ``onMultipleTokensMove`` is actually called,
         ``onTokenMove`` is called for each single token.

         If you use both events at the same time it is recommended that
         you use the ``tokens.moveCount`` variable in ``onTokenMove``
         and abort if its >1 and let ``onMultipleTokensMove`` handle it.

         If you dont know what event to use you probably want to use
         ``onTokenMove``.

         .. rubric:: How to set it up
            :name: how-to-set-it-up

         #. You need a `Library Token </rptools/wiki/Library_Token>`__.
            You'll find some details if you follow that link, but its
            simply a token named "Lib:something" that is a NPC and
            visible to players.
         #. On this token you place macros. If you want to use the event
            *onTokenMove* you create a macro named ``onTokenMove`` on
            it.

         Thats it. Yeah, it is so simple. For what you can really do
         with this you can see the examples below.

         .. rubric:: Special Variables
            :name: special-variables

         There are some special variables that are needed or useful in
         context of these events.

         | 
         | ```tokens.denyMove`` </rptools/wiki/tokens.denyMove>`__ has
           to be set to ``1`` to cancel the current movement.

         ```tokens.moveCount`` </rptools/wiki/tokens.moveCount>`__
         contains the number of tokens moved.

         .. rubric:: Paths
            :name: paths

         In context of these events there will sometimes be specified or
         returned a path or a list of coordinates. These are in this
         specific format:

         it is a json array containing json objects for each points.
         Each json object defines the keys ``x`` and ``y`` with the map
         coordinates.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: samplePath = json.append("",

               #. .. code:: de1

                         json.set("", "x", 50, "y", 50), 

               #. .. code:: de1

                         json.set("", "x",  0, "y",  0)

               #. .. code:: de1

                     )]

               #. .. code:: de2

                      

               #. .. code:: de1

                      

               #. .. code:: de1

                     <!-- samplePath contains 

               #. .. code:: de1

                     [{"x":50,"y":50},{"x":0,"y":0}]

               #. .. code:: de1

                      -->

         | 
         | If you have to construct coordinate arrays by hand you can
           use a simple drop-in tool that you can download here:
           `rptools-forums:
           shapeBuilder <http://forums.rptools.net/viewtopic.php?p=180113#p180113>`__

         .. rubric:: Related Functions
            :name: related-functions

         There is a number of functions that are very useful in
         combination with the onMove-events.

         .. rubric:: getLastPath()
            :name: getlastpath

         `getLastPath() </rptools/wiki/getLastPath>`__ returns the last
         path. Note that - if you use this in ``onTokenMove`` - it
         returns exactly the same as ``macro.args``. *(requires b74+)*

         .. rubric:: movedOverPoints(arrayOfCoordinates)
            :name: movedoverpointsarrayofcoordinates

         `movedOverPoints() </rptools/wiki/movedOverPoints>`__ returns
         an array of coordinates with all "hit" cells within a shape
         formed by the specified array of coordinates. *(requires b75+)*

         | 

         .. rubric:: movedOverToken(tokenName, [lastPath])
            :name: movedovertokentokenname-lastpath

         `movedOverToken() </rptools/wiki/movedOverToken>`__ returns an
         array of coordinates with all "hit" cells where the moved token
         crosses the specified token. *(requires b74+)*

         Note that before b77 the token must be specified by name - not
         id.

         .. rubric:: getMoveCount()
            :name: getmovecount

         `getMoveCount() </rptools/wiki/getMoveCount>`__ returns the
         calculated move cost according to the selected move metric.
         *(requires b76+)*

         .. rubric:: Examples
            :name: examples

         Lets now give you some simple examples for most commons use
         cases.

         .. rubric:: Traps/Teleporting
            :name: trapsteleporting

         An example of a trap macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:'<!-- this should be in onTokenMove -->']

               #. .. code:: de1

                     [h:'<!--Routine for a Trap, trap is only triggered when the subject is moved on or over the Trap Token "Spear Trap"-->']

               #. .. code:: de1

                     [h:'<!-- retrieve the path that the token has walked on -->']

               #. .. code:: de1

                     [h:lastPath     = getLastPath(1)]

               #. .. code:: de2

                     [h:'<!-- check if that path intersects with the trap token -->']

               #. .. code:: de1

                     [h:trapPadTriggered = movedOverToken("Spear Trap",lastPath)]

               #. .. code:: de1

                     [r, if(!json.isEmpty(trapPadTriggered)), CODE:{

               #. .. code:: de1

                      [h:'<!-- If so trigger the trap for that token, do note that this only works when ONE token is moved. -->']

               #. .. code:: de1

                         [h:me = getSelectedNames()]

               #. .. code:: de2

                      [h:switchToken(me)]

               #. .. code:: de1

                      

               #. .. code:: de1

                         [h:attackRoll = d20]

               #. .. code:: de1

                        [h:roll=1d6]

               #. .. code:: de1

                       [h,if(attackRoll > Dexterity):HP=HP-roll]

               #. .. code:: de2

                        [r,if(attackRoll > Dexterity):"You have triggered a trap and sustained "+roll+" hits.<br>"]

               #. .. code:: de1

                     };{}]

         An example of a Teleport macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:'<!-- Routine for a Teleport, this particular routine will move a token from a 

               #. .. code:: de1

                              teleport token called "Start 1" to another token called "End 1"->']

               #. .. code:: de1

                     [h:'<!-- Note that the big difference with the trap macro is that here you have to 

               #. .. code:: de1

                              stop on the teleport token for it to be triggered, while the trap triggered 

               #. .. code:: de2

                              when you move OVER OR ONTO the trap token ->']

               #. .. code:: de1

                     [h: targetToken = currentToken()]

               #. .. code:: de1

                     [h: lastPath    = getLastPath(1)]

               #. .. code:: de1

                     [h: padName     = "Start 1"]

               #. .. code:: de1

                     [h: teleporterTriggered = movedOverToken(padName,lastPath)]

               #. .. code:: de2

                     [h,token(targetToken): currentLocation = json.set("{}","x",getTokenX(),"y",getTokenY())]

               #. .. code:: de1

                      

               #. .. code:: de1

                     [h,if(json.contains(teleporterTriggered,currentLocation)), CODE:{

               #. .. code:: de1

                         [teleportEndName = replace(padName, "Start", "End")]

               #. .. code:: de1

                         [h:'<!-- This part makes sure that you end up on the same position on the end token as you started on the start token. E.g if you moved the PC onto the Upper left corner of "Start 1" then youll end up on the upper left corner of "End 1"" -->']

               #. .. code:: de2

                      

               #. .. code:: de1

                         [h:'<!-- Get the actual coordinates "Start 1" and "End 1" -->']

               #. .. code:: de1

                         [Token(padName):         startCentreX = getTokenX(1)]

               #. .. code:: de1

                         [Token(padName):         startCentreY = getTokenY(1)]

               #. .. code:: de1

                         [Token(teleportEndName): endCentreX   = getTokenX(1)]

               #. .. code:: de2

                         [Token(teleportEndName): endCentreY   = getTokenY(1)]

               #. .. code:: de1

                      

               #. .. code:: de1

                         [h:'<!-- Get the coordinates of the moved token -->']

               #. .. code:: de1

                         [h, Token(targetToken):CurrentX = getTokenX()]

               #. .. code:: de1

                         [h, Token(targetToken):CurrentY = getTokenY()]

               #. .. code:: de2

                      

               #. .. code:: de1

                         [h:'<!-- Calculate its relative position -->']

               #. .. code:: de1

                         [h:NewX = CurrentX + endCentreX - startCentreX]

               #. .. code:: de1

                         [h:NewY = CurrentY + endCentreY - startCentreY]

               #. .. code:: de1

                      

               #. .. code:: de2

                         [h:'<!-- move the token to the new location -->']

               #. .. code:: de1

                         [h, Token(targetToken):moveToken(NewX, Newy , 1 )]    

               #. .. code:: de1

                      

               #. .. code:: de1

                         [h:'<!-- centre view on the tokens new position. -->']

               #. .. code:: de1

                         [goto(targetToken)]

               #. .. code:: de2

                     };{}]

         Please note that there already exists a drop-in
         `[1] <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__
         that facilitates Traps and Teleports (among other things),
         which you can find on the forum. The tricky part is to get
         multiple 'special pads' working next to each other in
         combination with multiple tokens move.

         .. rubric:: Movement cost tracking
            :name: movement-cost-tracking

         A often requested feature is to track allowed movement. With
         the new events we can do that.

         The example expects the movement to be tracked with a property
         named *Movement*. You have to reset this property to some kind
         of *max movement* every round - eg by hand or by hooking it in
         your initiative handler.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- this should be in onTokenMove -->

               #. .. code:: de1

                     <!-- moved token is in context -->

               #. .. code:: de1

                      

               #. .. code:: de1

                     <!-- get movement -->

               #. .. code:: de2

                     [h: mov = getProperty("Movement")]

               #. .. code:: de1

                     [h: usedMov = getMoveCount()]

               #. .. code:: de1

                      

               #. .. code:: de1

                     <!-- deny move if not allowed, reduce mov prop otherwise -->

               #. .. code:: de1

                     [r, if( mov >= usedMov ), code: {

               #. .. code:: de2

                         [h: mov = mov - usedMov]

               #. .. code:: de1

                         [h: setProperty("Movement", mov)]

               #. .. code:: de1

                     };{

               #. .. code:: de1

                         [h: tokens.denyMove = 1]

               #. .. code:: de1

                         <span style="color:red;font-weight:bold;">Move limit exceeded.</span>    

               #. .. code:: de2

                     }]

         .. rubric:: Exposure of Fog on gridless maps
            :name: exposure-of-fog-on-gridless-maps

         Fog does not get cleared on gridless maps. But we can do this
         by using a simple onTokenMove-event.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- this should be in onTokenMove -->

               #. .. code:: de1

                     <!-- clear fog only if pc token moved -->

               #. .. code:: de1

                     [h, if( isPC() ): exposeFOW()]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Guide_to_onTokenMove&oldid=7586"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Guide+to+onTokenMove>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Guide_to_onTokenMove>`__
            -  `Discussion </maptool/index.php?title=Talk:Guide_to_onTokenMove&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Guide_to_onTokenMove>`__
            -  `View
               source </maptool/index.php?title=Guide_to_onTokenMove&action=edit>`__
            -  `View
               history </maptool/index.php?title=Guide_to_onTokenMove&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Guide_to_onTokenMove>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Guide_to_onTokenMove>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Guide_to_onTokenMove&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Guide_to_onTokenMove&oldid=7586>`__
            -  `Page
               information </maptool/index.php?title=Guide_to_onTokenMove&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 26 August 2019, at 13:25.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
