==========================
getTokenNames - MapToolDoc
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

   .. rubric:: getTokenNames
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

            -  `1 getTokenNames()
               Function <#getTokenNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenNames() Function
            :name: gettokennames-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the names of all the
            `tokens </rptools/wiki/Token>`__ on the current
            `map </maptool/index.php?title=Map&action=edit&redlink=1>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getTokenNames()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getTokenNames(delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getTokenNames(delim, conditions)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            String List that is returned, defaults to ``","``. If
            ``"json"`` is specified, a JSON array is returned instead of
            a String List.
         -  ``conditions`` - A JSON object that contains various
            conditions that the tokens must fullfill. All conditions are
            optional.

            -  ``setStates`` - A JSON array of states the token must
               have. Any token which does not contain all of these
               states in the ``true`` condition will be removed from the
               returned list.
            -  ``unsetStates`` - A JSON array of states the token must
               **not** have.
            -  ``npc`` - If the token must be a NPC, set to
               ``true``\ (``1``) or ``false``\ (``0``).
            -  ``pc`` - If the token must be a PC, set to
               ``true``\ (``1``) or ``false``\ (``0``).
            -  ``selected`` - If the token must be selected, set to
               ``true``\ (``1``) or ``false``\ (``0``).
            -  ``impersonated`` - If the token must be impersonated, set
               to ``true``\ (``1``) or ``false``\ (``0``).
            -  ``current`` - If the token must be the current token, set
               to ``true``\ (``1``) or ``false``\ (``0``).
            -  ``owned`` - If the token must be owned by the current
               player, set to ``true``\ (``1``) or ``false``\ (``0``).
            -  ``visible`` - If the token must be visible to players,
               set to ``true``\ (``1``) or ``false``\ (``0``).

               -  note: GMs will be able to see everything, to test if a
                  token is visible to a player with this function, you
                  must have "Show as a Player" enabled. In addition,
                  this appears to only affect the "visible to players"
                  flag - VBL and Fog of War do not seem to affect this.

            -  ``layer`` - A JSON array of layer names, or a single
               layer name as a string. Note that a token not on any of
               the listed layers will be removed from the list returned
               (added in **1.3b77**)
            -  ``range`` - A JSON object with range conditions, all
               range conditions are optional.

               -  ``token`` - The id or name of the source token that
                  the distance is measured from, defaults to the current
                  token.

                  -  note: this parameter is needed if you are calling
                     your macro from a macroLink and aren't
                     impersonating a token.

               -  ``distancePerCell`` - If the Distance Per Cell
                  multiplier should be used, set to ``true``\ (``1``) or
                  ``false``\ (``0``).
               -  ``from`` - A number specifying the minimum range that
                  a token needs to be from the source.
               -  ``upto`` - A number specifying the maximum range that
                  a token can be from the source.
               -  ``metric`` - The distance metric to use, if it is not
                  specified the default from the users preferences is
                  used.

            -  ``area`` - A JSON object containing specific area
               information.

               -  ``token`` - An optional field that contain the name or
                  id of the token that resides at the center of the
                  area. Defaults to the current token.
               -  ``offsets`` - A JSON array of JSON objects that
                  specify each individual cell that make up the area.

                  -  ``x`` - The relative ``x`` position of the cell in
                     relation to the ``token`` field. Measured in cells.
                  -  ``y`` - The relative ``y`` position of the cell in
                     relation to the ``token`` field. Measured in cells.

         | 
         | The movement metric in range specifies the movement metric
           use, the metric can be one of the following strings:

         -  ``NO_GRID`` - The grid is ignored and straight line distance
            between the tokens is returned.
         -  ``ONE_TWO_ONE`` - First Diagonal movement costs 1, second 2,
            and so on (Square grid only).
         -  ``ONE_ONE_ONE`` - Diagonal movement costs a single square
            (Square grid only).
         -  ``MANHATTAN`` - Diagonal movement costs 2 (Square grid
            only).
         -  ``NO_DIAGONALS`` - No diagonal movement is allowed (Square
            grid only).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            \*You can use the following code to print out the names of
            all of the tokens on the current map:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: names = getTokenNames()]

                  #. .. code:: de1

                        [foreach(name, names, "<br>"): name]

            -  Find and return a `JSON
               Array </rptools/wiki/JSON_Array>`__ containing all NPC
               tokens' names that are within 2 squares or hexes:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: cond = '{ range: {upto:2, distancePerCell:0}, npc:1 }']

                  #. .. code:: de1

                        [h: names = getTokenNames("json", cond)]

            -  Modifying the above example to exclude dead tokens:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: cond = '{ range: {upto:2, distancePerCell:0}, npc:1, unsetStates:["Dead"] }']

                  #. .. code:: de1

                        [h: names = getTokenNames("json", cond)]

            -  Get all of the non dead NPC tokens' names in the square
               above, below, left, and to the right of the token, using
               the ``area`` option:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: areaOffsets = '[ {x:1, y:0}, {x:0, y:1}, {x:-1, y:0}, {y:-1, x:0}]']

                  #. .. code:: de1

                        [h: area = json.set("{}", "offsets", areaOffsets)]

                  #. .. code:: de1

                        [h: cond = json.set("{}", "area", area, "npc", 1, "unsetState", "['Dead']")]

                  #. .. code:: de1

                        [h: names = getTokenNames("json", cond)]

            -  The same could be achieved using the ``range`` option
               with ``NO_DIAGONALS`` metric:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']

                  #. .. code:: de1

                        [h: names = getTokenNames("json", cond)]

            -  Get ALL tokens on a map:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r:allToks = getTokenNames(",",'{layer:["TOKEN", "HIDDEN", "OBJECT", "BACKGROUND"]}')]

            or better:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r:getTokens(",", json.set("{}", "layer", json.append("[]","TOKEN","HIDDEN","OBJECT","BACKGROUND")))]

            | 
            | Please Note that it, in general, is bad practice to create
              json objects and arrays by hand. This makes your code very
              bug prone. The proper way is to build your json objects
              through code.
            | E.g.:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: cond = '{ range: {upto:1, distancePerCell:0, metric:"NO_DIAGONALS"}, npc:1, unsetStates:["Dead"] }']

            can better be created with

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: cond = json.set("{}", "range", json.set("{}", "upto", 1, "distancePerCell", 0, "metric", "NO_DIAGONALS"), "npc", 1, "unsetStates", json.append("[]","Dead"))]

            | The big difference between the two methods is that, doing
              it by hand, it is quite likely that when you make a
              mistake your code appears to 'work', that is you get no
              error reports, but only part of the conditions are met
              because you e.g. used ``''`` or ``""`` where you should
              not have.

            If you make a mistake in the automated method, there is a
            bigger chance you get an error report, allowing you to fix
            it. Of course typos like ``'ragne'`` instead of ``'range'``
            won't trigger any errors.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.
            -  **1.3b51** - Added ``conditions`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenNames&oldid=6063"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Token
               Function </rptools/wiki/Category:Token_Function>`__
            -  `Find Function </rptools/wiki/Category:Find_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Find
         Function </rptools/wiki/Category:Find_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Token
         Function </rptools/wiki/Category:Token_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getTokenNames>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getTokenNames>`__
            -  `Discussion </maptool/index.php?title=Talk:getTokenNames&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getTokenNames>`__
            -  `View
               source </maptool/index.php?title=getTokenNames&action=edit>`__
            -  `View
               history </maptool/index.php?title=getTokenNames&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getTokenNames>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getTokenNames>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getTokenNames&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getTokenNames&oldid=6063>`__
            -  `Page
               information </maptool/index.php?title=getTokenNames&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 22 February 2013, at 12:51.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
