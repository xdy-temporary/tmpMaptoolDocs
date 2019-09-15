======================
copyToken - MapToolDoc
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

   .. rubric:: copyToken
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

            -  `1 copyToken() Function <#copyToken.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Parameters <#Parameters>`__
               -  `1.3 Updates parameter <#Updates_parameter>`__
               -  `1.4 How to make additional changes to the newly
                  created
                  token <#How_to_make_additional_changes_to_the_newly_created_token>`__

            -  `2 examples <#examples>`__
            -  `3 examples of updates after
               copy <#examples_of_updates_after_copy>`__
            -  `4 also <#also>`__
            -  `5 changes <#changes>`__

         .. rubric:: copyToken() Function
            :name: copytoken-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Creates one or more copies of a
            `Token </rptools/wiki/Token>`__ and returns the id of the
            created copy. This function is used to copy
            `Tokens </rptools/wiki/Token>`__ into the current map, the
            `Tokens </rptools/wiki/Token>`__ you are making
            copies of can reside on any map. **You can not make any
            modifications to the newly
            created**\ `Tokens </rptools/wiki/Token>`__\ **in the macro
            that creates them**. Any changes made to the newly created
            token are reverted as soon as the macro ends! As of b54
            there is a new parameter that allows you to make some
            changes to the new tokens.

            **Note:** below you can find several methods on how to make
            changes to the newly created

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     copyToken(id)

               #. .. code:: de1

                     copyToken(id, numCopies)

               #. .. code:: de1

                     copyToken(id, numCopies, fromMap)

               #. .. code:: de1

                     copyToken(id, numCopies, fromMap, updates)

               #. .. code:: de2

                     newId = copyToken(id, numCopies, fromMap, updates)

         | 

         .. rubric:: Parameters
            :name: parameters

         -  ``id`` - The id or name of the token to copy.
         -  ``numCopies`` - The number of copies to create, defaults to
            ``1``
         -  ``fromMap`` - The name of the map to copy from, defaults to
            the current map.
         -  ``updates`` - a `JSON Object </rptools/wiki/JSON_Object>`__
            that contains updates to be made to the copied
            `Tokens </rptools/wiki/Token>`__.

         You can use an empty string ("") for ``fromMap`` for the
         current map as of b54.

         | 
         | The return type of this function is determined by the number
           of copies that you are making. If you are only creating a
           single copy of the token then a string containing the
           `Tokens </rptools/wiki/Token>`__ id, if you are making more
           than one copy then a `JSON
           Array </rptools/wiki/JSON_Array>`__ containing the
           `Token </rptools/wiki/Token>`__ ids of all the newly created
           `Tokens </rptools/wiki/Token>`__ is returned.

         | 

         .. rubric:: Updates parameter
            :name: updates-parameter

         ``updates`` is a `JSON Object </rptools/wiki/JSON_Object>`__
         that can contain one or more of the following fields. Field
         names are case-sensitive.

         -  ``name`` - The name of the new
            `Token </rptools/wiki/Token>`__.
         -  ``label`` - The label for the new
            `Token </rptools/wiki/Token>`__.
         -  ``gmName`` - The GM name for the new
            `Token </rptools/wiki/Token>`__.
         -  ``layer`` - The layer for the new
            `Token </rptools/wiki/Token>`__.
         -  ``x`` - The X Co-ordinate for the new
            `Token </rptools/wiki/Token>`__. Default is ``0``.
         -  ``y`` - The Y Co-ordinate for the new
            `Token </rptools/wiki/Token>`__. Default is ``0``.
         -  ``useDistance`` - ``1`` (true) or ``0`` (false). Determines
            if the "Distance Per Cell" measurement for the map is used
            for the x,y coordinates. Unused if neither ``x`` nor ``y``
            is specified. Default is false. Use ``1`` (true) for tokens
            that are not snap-to-grid and must be placed by pixel
            position instead of grid cell position.
         -  ``facing`` - Sets the facing for the
            `Token </rptools/wiki/Token>`__. If the
            `Token </rptools/wiki/Token>`__ is on the background or
            object layer this sets the rotation.
         -  ``size`` - Sets the size of the
            `Token </rptools/wiki/Token>`__. The list of sizes is
            dependent on the type of grid.
         -  ``delta`` - ``1`` (true) or ``0`` (false). Indicates whether
            the x,y coordinates are relative to the position of the
            original token. **Added in 1.3b77.**
         -  ``tokenImage`` / ``portraitImage`` / ``handoutImage`` -
            Changes the coresponding image. Value can be either an
            assetId or an image token name. **Added in 1.3b77.**

         The values for all of these fields are evaluated so all text
         within ``{}`` or ``[]`` goes through the standard macro
         processing. There is currently no way to modify the new token
         from inside these macro commands, however.

         When the name is not changed using the ``updates`` parameter,
         the new name for the token follows the naming method for cut
         and paste. This function can copy
         `Tokens </rptools/wiki/Token>`__ in the token, hidden, object,
         and background layers. If you do not override the destination
         using the ``layer`` field of ``updates`` then the new copies
         are made in the same layer as the source. Likewise if ``x`` and
         ``y`` are not specified then these locations are the same as
         the source.

         | 

         .. rubric:: How to make additional changes to the newly created
            token
            :name: how-to-make-additional-changes-to-the-newly-created-token

         As said, ANY changes made to the new token will be reverted as
         soon as the macro ends. However there are a couple of methods
         to do it anyway.

         1 The most reliable and straightforward method is to change the
         ORIGINAL token first and then copy it. You \*can\* revert the
         changes to the original after the copyToken. However if the
         original token is not on the same map then you can't
         immediately change the original. To solve that here some
         methods:

         a. The best methods in that case is to
         `moveTokenFromMap() </rptools/wiki/moveTokenFromMap>`__ to the
         current map and then
         `moveTokenToMap() </rptools/wiki/moveTokenToMap>`__ back.

         b. You could also use
         `setCurrentMap() </rptools/wiki/setCurrentMap>`__) to go to the
         'original' map, change the token and switch back, that however
         will result in a minor flicker on screen.

         c. A final alternative is adding the 'lib:' prefix to the
         original, that way its properties are accessible throughout all
         maps

         2. The simplest method is by creating an interrupt in the macro
         after the copies have been made. This is simply done with the
         use of `input() </rptools/wiki/input>`__. This however will
         result in a pop-up on screen which you have to click away so
         the macro can continue with the update.

         3. Another (not always working method) is to make changes to
         the created tokens done by a second 'deferred' macro that is
         called after the copies have been created. Look for
         `execLink </rptools/wiki/execLink>`__ for calling a macro
         *deferred*.

         | 

         .. rubric:: examples
            :name: examples

         Make a single copy of the Hero from the current map.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: copyToken("Hero")]

         Make a single copy of the Hero from another map.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: copyToken("Hero", 1, "Green Room")]

         Or if you are playing paranoia and want to create six clones.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: copyToken("Hero", 6, "Clone Vat")]

         But as a PC the new tokens don't get new names so we could give
         each of them a new name in b54+ using the following.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de1

                     [h: updates = "{ 

               #. .. code:: de1

                                      name: 'Hero Clone - [r: cloneNo = cloneNo + 1]'

               #. .. code:: de1

                                    }"

               #. .. code:: de2

                     ]

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de1

                     [h: copyToken("Hero", 6, "Clone Vat", updates)]

         This will copy all our clones to the current map but they are
         all on top of each other, to line them up

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de1

                     [h: x = 0]

               #. .. code:: de1

                     [h: updates = "{ 

               #. .. code:: de1

                                      name: 'Hero Clone - [r: cloneNo = cloneNo + 1]',

               #. .. code:: de2

                                      x: '[r: x = x + 2]',

               #. .. code:: de1

                                      y: 0

               #. .. code:: de1

                                    }"

               #. .. code:: de1

                     ]

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de2

                     [h: copyToken("Hero", 6, "Clone Vat", updates)]

         Or combining rotation

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de1

                     [h: x = 0]

               #. .. code:: de1

                     [h: facing = 0]

               #. .. code:: de1

                     [h: updates = "{ 

               #. .. code:: de2

                                      name: 'Hero Clone - [r: cloneNo = cloneNo + 1]',

               #. .. code:: de1

                                      x: '[r: x = x + 2]',

               #. .. code:: de1

                                      y: 0,

               #. .. code:: de1

                                      facing: '[r: facing = facing + 40]'

               #. .. code:: de1

                                    }"

               #. .. code:: de2

                     ]

               #. .. code:: de1

                     [h: cloneNo = 0]

               #. .. code:: de1

                     [h: copyToken("Hero", 6, "Clone Vat", updates)]

         And now we have tumbling clones:

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image0|

                  .. container:: thumbcaption

                     Tumbling Clones using Top-down Tokens

         The source token was configured as a Top Down token for this
         effect, otherwise the ``facing`` setting would produce a facing
         arrow for `Tokens </rptools/wiki/Token>`__ on the token or
         hidden layers.

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image1|

                  .. container:: thumbcaption

                     Tumbling Clones using Round Tokens and Facing
                     Arrows

         This example shows using the new ``delta`` parameter available
         in **1.3b77**. Specifying ``true`` means all x,y coordinates
         are treated as offsets from the original token. They are
         measured in grid cells if ``useDistance`` is false (the
         default) or in pixels if ``true``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: x = 0]

               #. .. code:: de1

                     [h: updates = "{ 

               #. .. code:: de1

                         x: '[r: x = x + 2]',

               #. .. code:: de1

                         delta: 1,

               #. .. code:: de2

                     }" ]

               #. .. code:: de1

                     [h: copyToken(currentToken(), 3, "", updates)]

         Make three copies of the currently selected token on the
         current map. Place the first copy two grid cells to the right
         of the original token. (Note that the trailing comma after
         ``delta: 1`` is ignored by MapTool.)

         .. rubric:: examples of updates after copy
            :name: examples-of-updates-after-copy

         Simplest method:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:id=copyToken("Hero")]

               #. .. code:: de1

                     [h:input("junk|This interruption is required to create the new token. Click ok to continue.|Message |LABEL")]

               #. .. code:: de1

                     [h:setProperty("Strength", 3d6,id)]

         Straightforward method:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:moveTokenFromMap("Hero", "Grasslands")]

               #. .. code:: de1

                     [h:setProperty("Strength", 3d6, "Hero")]

               #. .. code:: de1

                     [h:moveTokenToMap("Hero", "Grasslands")]

               #. .. code:: de1

                     [h:copyToken("Hero", 1, "Grasslands")]

         Fancy method that leave the original token unchanged

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:moveTokenFromMap("Hero", "Grasslands")]

               #. .. code:: de1

                     <!-- swap from name to token id as tokens with the same name will soon exist -->

               #. .. code:: de1

                     [h:origId = findToken("Hero")]

               #. .. code:: de1

                     <!-- copy original with same name -->

               #. .. code:: de2

                     [h:origCopyId = copyToken("Hero", 1, "", "{name: 'Hero'}")]

               #. .. code:: de1

                     <!-- update original with new properties -->

               #. .. code:: de1

                     [h:setProperty("Strength", 3d6, origId)]

               #. .. code:: de1

                     <!-- copy and then delete original -->

               #. .. code:: de1

                     [h:copyToken(origId, 1)]

               #. .. code:: de2

                     [h:removeToken(origId)]

               #. .. code:: de1

                     <!-- move the copy from BEFORE the changes back to the original map -->

               #. .. code:: de1

                     [h:moveTokenToMap(origCopyId, "Grasslands")]

         .. rubric:: also
            :name: also

         `moveTokenToMap() </rptools/wiki/moveTokenToMap>`__,
         `moveTokenFrom() </rptools/wiki/moveTokenFrom>`__

         .. rubric:: changes
            :name: changes

         -  **1.3b54** - Added optional ``updates`` parameter.
         -  **1.3b77** - Added ``tokenImage``, ``portraitImage``,
            ``handoutImage``, and ``delta`` to ``updates``.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=copyToken&oldid=6864"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Token
               Function </rptools/wiki/Category:Token_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
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
            in </maptool/index.php?title=Special:UserLogin&returnto=copyToken>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/copyToken>`__
            -  `Discussion </maptool/index.php?title=Talk:copyToken&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/copyToken>`__
            -  `View
               source </maptool/index.php?title=copyToken&action=edit>`__
            -  `View
               history </maptool/index.php?title=copyToken&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/copyToken>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/copyToken>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=copyToken&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=copyToken&oldid=6864>`__
            -  `Page
               information </maptool/index.php?title=copyToken&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 12 January 2017, at 12:10.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |image0| image:: /maptool/images/d/d1/TumblingClones.jpeg
   :class: thumbimage
   :width: 694px
   :height: 114px
   :target: /rptools/wiki/File:TumblingClones.jpeg
.. |image1| image:: /maptool/images/3/32/PointingClones.jpeg
   :class: thumbimage
   :width: 694px
   :height: 114px
   :target: /rptools/wiki/File:PointingClones.jpeg
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
