============================================
Introduction to Vision Blocking - MapToolDoc
============================================

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

   .. rubric:: Introduction to Vision Blocking
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

         .. container:: template_languages

            Languages:  English
             • \ `español </rptools/wiki/Introduction_to_Vision_Blocking/es>`__\  • \ `français </rptools/wiki/Introduction_to_Vision_Blocking/fr>`__\ 
             • \ `日本語 </rptools/wiki/Introduction_to_Vision_Blocking/ja>`__\ 

         .. container:: template_beginner

            | BEGINNER
            | THIS IS A BEGINNER ARTICLE

         | 

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Vision Blocking <#Vision_Blocking>`__

               -  `1.1 First, Get a Map <#First.2C_Get_a_Map>`__

            -  `2 Activating the Vision Blocking
               Tools <#Activating_the_Vision_Blocking_Tools>`__

               -  `2.1 Best Practices <#Best_Practices>`__

            -  `3 Putting VBL on the Sample
               Map <#Putting_VBL_on_the_Sample_Map>`__

               -  `3.1 Cover the Entire Dungeon with Solid
                  VBL <#Cover_the_Entire_Dungeon_with_Solid_VBL>`__
               -  `3.2 Cut out the Visible Areas from the Solid
                  VBL <#Cut_out_the_Visible_Areas_from_the_Solid_VBL>`__
               -  `3.3 Interior VBL <#Interior_VBL>`__
               -  `3.4 VBL and Objects <#VBL_and_Objects>`__

            -  `4 VBL Limitations <#VBL_Limitations>`__

         .. rubric:: Vision Blocking
            :name: vision-blocking

         In MapTool, `tokens </rptools/wiki/Token:token>`__ can be given
         `sight </rptools/wiki/Introduction_to_Lights_and_Sights>`__,
         which lets the program model vision and lighting in-game. In
         other words, when you configure the token with vision, it can
         then "see" other tokens and areas of the map. In addition,
         MapTool provides for
         `lighting </rptools/wiki/Introduction_to_Lights_and_Sights>`__
         - so a token can "see" only to the extent of its light source
         (or nearby light sources) - and Vision Blocking, which lets you
         establish boundaries to the token's visual range (so you can
         indicate where the walls are in a dungeon, for instance).

         This introductory element will briefly review the Vision
         Blocking Layer tools in MapTool (sometimes also called
         *topology* tools), and how to use them to create a sample
         dungeon environment. Remember, Vision Blocking is intimately
         connected to the **Sight**, **Light**, and **Fog of War**
         features of MapTool, so once you've read this tutorial, go
         check out the `Introduction to Lights and
         Sights </rptools/wiki/Introduction_to_Lights_and_Sights>`__ and
         see how it all works together!

         .. rubric:: First, Get a Map
            :name: first-get-a-map

         .. container:: thumb tright

            .. container:: thumbinner

               |image0|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:samp-dungeon.png>`__

                  Sample Dungeon

         To start off, we'll need a map of a dungeon. Somewhere suitably
         subterranean and dank, full of twisty little passages, all
         alike.

         Well, maybe we won't get too crazy with the mazes of twisty
         passages. Created using an `awesome
         tileset <http://forums.rptools.net/viewtopic.php?f=34&t=7418>`__
         created by Jonathan Roberts (Torstan on the `RPTools
         Forums <http://forums.rptools.net>`__), the map shown to the
         right will be used for the examples in this introductory
         tutorial.

         .. rubric:: Activating the Vision Blocking Tools
            :name: activating-the-vision-blocking-tools

         .. container:: thumb tright

            .. container:: thumbinner

               |image1|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-toolbar-btn.png>`__

                  The VBL toolbar button

         .. container:: thumb tright

            .. container:: thumbinner

               |image2|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-tools.png>`__

                  The VBL tools, activated when you click on the VBL
                  toolbar button

         To activate the Vision Blocking Tools, click on the "Eye" icon
         in the MapTool toolbar. (eye icon screenshot). When you do so,
         a new set of buttons will appear - these are the various Vision
         Blocking drawing tools you can use. If you hover over them, a
         tooltip will pop up explaining what each one does. From left to
         right, they are:

         -  **Draw a Rectangular VBL**: this creates solid rectangular
            areas that block vision (these are generally called Vision
            Blocking Layers, or "VBL" for short). . Tokens outside the
            area cannot see into it or through it; tokens inside the
            area cannot see anything at all (it is solid and opaque).
         -  **Draw a Hollow Rectangular VBL**: this, as it implies,
            creates hollow VBL - if a token is *inside* the area, they
            will see everything inside it, but will not be able to see
            *beyond* the boundary; for tokens outside the VBL area, they
            will see everything outside, but cannot see *into* the
            rectangular area.
         -  **Draw a Circular VBL**: like the rectangular one, this
            creates a circular (in reality, a polygon approximating a
            circular area; actual circular curves are
            performance-intensive!) VBL
         -  **Draw a Hollow Circular VBL**: behaves like the hollow
            rectangle
         -  **Draw Closed Poly Line VBL**: this lets you draw an
            arbitrary polygonal shape using line segments, and when
            finished, closes it and makes a solid VBL out of it. To
            start the polyline shape, left-click on the map, and draw
            the first segment. To attach the next segment, *right-click*
            and move the mouse to create the next line segment. When
            finished with the full shape, left-click to close it.
         -  **Draw Poly line VBL**: as above, but creates a hollow
            polygon

         .. rubric:: Best Practices
            :name: best-practices

         Vision blocking and vision processing is processor-intensive,
         and overuse of (or overly-complex) VBL can cause serious
         performance issues with MapTool - slowdowns, inability to
         navigate a map, and so forth. Some rules of thumb:

         #. **Use square VBL wherever possible** - and minimize the use
            of circular or highly irregular VBL
         #. **Use solid VBL wherever possible** - this prevents gaps
            between polylines, which can be performance hogs. Instead,
            cover the map with VBL, and cut out the areas that the
            tokens should be able to see.
         #. **Use as little VBL as necessary to get the effect you
            seek** - make it efficient!
         #. It is frequently a good idea to set up a vision boundary at
            the edges of the play area on your map - maps in MapTool are
            theoretically infinitely sized, but if your tokens are going
            to be only in the dungeon area, there's no reason for
            MapTool to have to be calculating what they see all the way
            out to the edge of the universe.

         These will help keep performance from bogging down. You *can*
         use the other kinds of VBL, but simply be aware of how complex
         your vision blocking setup is getting.

         .. rubric:: Putting VBL on the Sample Map
            :name: putting-vbl-on-the-sample-map

         Now, to add some vision blocking to the map. We will use a
         recommended technique, which is to cover the entire map with a
         solid block of VBL, and then "cut out" of that block the areas
         that the players will see.

         .. rubric:: Cover the Entire Dungeon with Solid VBL
            :name: cover-the-entire-dungeon-with-solid-vbl

         .. container:: thumb tright

            .. container:: thumbinner

               |image3|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-map-zoomed-extents.png>`__

                  Zooming out so the entire dungeon area is visible

         .. container:: thumb tright

            .. container:: thumbinner

               |image4|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-createsolidvbl.png>`__

                  Creating a block of solid VBL over the whole dungeon

         #. Zoom the map so you can see the whole thing.
         #. Select the Draw a Rectangular VBL button.
         #. Left-Click to place the upper-left corner of the solid VBL.
            Do not hold down the left-mouse button.
         #. Drag the mouse to define the size of the VBL. You'll see it
            traced out in a transparent red color as you drag.
         #. Click the left mouse button again to place the lower-right
            corner of the VBL. The VBL will turn blue (if you go to the
            toolbar and select one of the other tools on the left side -
            switching off the VBL tools - the blue VBL indicators will
            disappear. They are only visible when the VBL tools are
            active).

         .. container:: thumb tright

            .. container:: thumbinner

               |image5|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-complete-cover.png>`__

                  The entire dungeon area covered by solid VBL

         You've now covered the entire map with VBL. If a token was
         placed outside that area, and had a "sight" setting active, it
         would not be able to see into that area.

         .. rubric:: Cut out the Visible Areas from the Solid VBL
            :name: cut-out-the-visible-areas-from-the-solid-vbl

         .. container:: thumb tright

            .. container:: thumbinner

               |image6|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-erasingvbl.png>`__

                  Erasing a section of VBL - hold down Ctrl to make the
                  area snap to the map grid.

         Now, we cut out the rooms. This process is a bit trickier - to
         keep the VBL efficient, make sure you get the edges lined up as
         best you can and you don't leave any narrow gaps or thin lines
         of VBL between rooms (a trick to doing this is in the
         instructions below). For this part, I will be clearing all VBL,
         out to the outer walls. We will work on the interior walls
         later.

         #. Zoom the map until you are comfortable with the zoom level.
         #. Select the Draw a Rectangular VBL tool.
         #. Hold down the Shift key, and left-click to mark the
            upper-left corner of the area of VBL you want to erase. A
            white, transparent box will follow the mouse cursor (if it's
            not white, you forgot to hold shift!)
         #. Drag the mouse until you've reached where you want the
            lower-right corner of the cleared area to be, and
            left-click. The blue VBL will disappear. You have now erased
            the VBL for that area, and tokens in that area would be able
            to see (their vision would be blocked, of course, once it
            reached any VBL!).
         #. Repeat this process for the rest of the rooms, tunnels, and
            so forth.

         .. container:: thumb tright

            .. container:: thumbinner

               |image7|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-erased.png>`__

                  The VBL is now erased over the dungeon rooms
                  themselves.

         Afterwards, you'll have a large blue area, with the dungeon
         "cut out" inside it.

         **TIP**: if you hold down Ctrl while you trace your VBL, it
         will snap to the gridlines of the map. This is very useful for
         aligning VBL. I used this technique to erase the VBL on the
         sample map, because it makes the VBL align easily and squarely
         on the dungeon walls.

         .. rubric:: Interior VBL
            :name: interior-vbl

         .. container:: thumb tright

            .. container:: thumbinner

               |image8|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-polyline-wall.png>`__

                  Drawing VBL on the walls with the Poly Line VBL tool.

         Finally, we will put VBL on the interior walls. This will make
         it so that the walls *inside* the dungeon block vision too.

         #. Zoom the map to focus on a particular wall.
         #. Select the "Draw Polyline VBL" tool.
         #. Hold down Ctrl, and left-click on the map to place the
            beginning of the line segment. I recommend starting the line
            somewhere in the solid VBL, so that there are no gaps at the
            edges of the walls.
         #. Drag the mouse to draw the line segment. (in the screenshot,
            the line segment is the thin red line inside the yellow
            circle; the yellow circle was drawn on the screenshot to
            show you where the polyline is - it's not part of the VBL
            process)
         #. Left-click to place the end of the line segment. The red
            line will turn blue, indicating that there is VBL now on
            that wall.
         #. Repeat the process for the other walls, until you are
            satisfied.

         .. rubric:: VBL and Objects
            :name: vbl-and-objects

         There are lots of objects in a dungeon that can block vision -
         doors, pillars, piles of rubble, chests...you name it. It is
         possible to draw VBL anywhere on a map - however, at this time,
         VBL is not linked to particular objects. This means that you
         can't, for instance, put VBL on a door and have it "open" with
         the door when your players open it. You can simulate this by
         deleting the VBL that crossed the doorway, but you can't have
         the VBL automatically move with an object.

         You'll have to experiment with the VBL for the objects in your
         dungeon, but here are some tips:

         -  **Doors**: for doors, if they are closed, simply draw the
            VBL along the wall in which the door sits. When (if) the
            door is ever opened, you can rotate the door object, and use
            Solid Rectangular VBL to erase the vision blocking layer
            that covered the doorway (remember, hold down Shift to erase
            VBL). Make sure to use *solid* VBL - if you use a hollow
            rectangle, it will only erase where the hollow rectangle's
            boundary intersects the other VBL.

         .. container:: thumb tright

            .. container:: thumbinner

               |image9|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Vbl-drawx.png>`__

                  An "X" drawn with VBL, typically used for pillars,
                  statues, and similar objects

         -  **Pillars, statues, and standing objects**: remember that,
            when you use VBL, the tokens cannot see into or through it
            at all (and, because of this, the *players* won't see
            anything covered by or hidden inside VBL on their screens).
            If you want the players to be able to see some of an object
            - like a large pillar - one of the recommended tricks is to
            draw an "X" on the pillar using poly line VBL (instead of
            covering the whole pillar with a circular or rectangular
            solid VBL. Using an X means that the players can see some of
            the pillar, depending on where their tokens are. It makes
            for a much nicer look. If you look at the screenshot, you'll
            see an "X" drawn using VBL on top of one of the barrels.

         .. rubric:: VBL Limitations
            :name: vbl-limitations

         The Vision Blocking Layer in MapTool is a tool for helping to
         simulate what a character can see during a game. However, it
         does have limitations, and doesn't "completely simulate vision"
         or anything like that. We touched on one limitation earlier,
         the fact that VBL cannot be attached to specific objects, and
         so if you open a door that is covered by VBL - the door object
         might move, but the VBL stays put. Here are a couple other
         limitations of the current (as of MapTool 1.3.b56) Vision
         Blocking Tools.

         -  **Vision Blocking is Binary**: VBL in MapTool is on or off.
            There is no "partially transparent" or "one way" VBL in the
            current version of MapTool.
         -  **Vision Blocking is Total**: Related to the above, VBL
            blocks all forms of vision. There are no vision types
            currently that can see through VBL.
         -  **Vision Blocking has no Elevation**: VBL cannot at this
            point be given a particular height - it stretches to
            infinity, up and down, and so there's no way to set up VBL
            so a tall character can see "over" it

         | 

         .. container:: template_languages

            Languages:  English
             • \ `español </rptools/wiki/Introduction_to_Vision_Blocking/es>`__\  • \ `français </rptools/wiki/Introduction_to_Vision_Blocking/fr>`__\ 
             • \ `日本語 </rptools/wiki/Introduction_to_Vision_Blocking/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Vision_Blocking&oldid=4109"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `MapTool </rptools/wiki/Category:MapTool>`__
            -  `Tutorial </rptools/wiki/Category:Tutorial>`__
            -  `Beginner </rptools/wiki/Category:Beginner>`__

         --------------

         `Beginner </rptools/wiki/Category:Beginner>`__
         `MapTool </rptools/wiki/Category:MapTool>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Tutorial </rptools/wiki/Category:Tutorial>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Introduction+to+Vision+Blocking>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Introduction_to_Vision_Blocking>`__
            -  `Discussion </maptool/index.php?title=Talk:Introduction_to_Vision_Blocking&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Introduction_to_Vision_Blocking>`__
            -  `View
               source </maptool/index.php?title=Introduction_to_Vision_Blocking&action=edit>`__
            -  `View
               history </maptool/index.php?title=Introduction_to_Vision_Blocking&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Introduction_to_Vision_Blocking>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Introduction_to_Vision_Blocking>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Introduction_to_Vision_Blocking&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Introduction_to_Vision_Blocking&oldid=4109>`__
            -  `Page
               information </maptool/index.php?title=Introduction_to_Vision_Blocking&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `español <http://lmwcs.com/rptools/wiki/Introduction_to_Vision_Blocking/es>`__
            -  `français <http://lmwcs.com/rptools/wiki/Introduction_to_Vision_Blocking/fr>`__
            -  `日本語 <http://lmwcs.com/rptools/wiki/Introduction_to_Vision_Blocking/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 17 January 2010, at 15:32.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |image0| image:: /maptool/images/thumb/0/0d/samp-dungeon.png/300px-samp-dungeon.png
   :class: thumbimage
   :width: 300px
   :height: 271px
   :target: /rptools/wiki/File:samp-dungeon.png
.. |image1| image:: /maptool/images/thumb/e/e7/Vbl-toolbar-btn.png/300px-Vbl-toolbar-btn.png
   :class: thumbimage
   :width: 300px
   :height: 111px
   :target: /rptools/wiki/File:Vbl-toolbar-btn.png
.. |image2| image:: /maptool/images/thumb/d/dc/Vbl-tools.png/300px-Vbl-tools.png
   :class: thumbimage
   :width: 300px
   :height: 76px
   :target: /rptools/wiki/File:Vbl-tools.png
.. |image3| image:: /maptool/images/thumb/7/77/Vbl-map-zoomed-extents.png/300px-Vbl-map-zoomed-extents.png
   :class: thumbimage
   :width: 300px
   :height: 230px
   :target: /rptools/wiki/File:Vbl-map-zoomed-extents.png
.. |image4| image:: /maptool/images/thumb/e/ea/Vbl-createsolidvbl.png/300px-Vbl-createsolidvbl.png
   :class: thumbimage
   :width: 300px
   :height: 230px
   :target: /rptools/wiki/File:Vbl-createsolidvbl.png
.. |image5| image:: /maptool/images/thumb/c/c7/Vbl-complete-cover.png/300px-Vbl-complete-cover.png
   :class: thumbimage
   :width: 300px
   :height: 223px
   :target: /rptools/wiki/File:Vbl-complete-cover.png
.. |image6| image:: /maptool/images/thumb/8/8f/Vbl-erasingvbl.png/300px-Vbl-erasingvbl.png
   :class: thumbimage
   :width: 300px
   :height: 230px
   :target: /rptools/wiki/File:Vbl-erasingvbl.png
.. |image7| image:: /maptool/images/thumb/0/07/Vbl-erased.png/300px-Vbl-erased.png
   :class: thumbimage
   :width: 300px
   :height: 223px
   :target: /rptools/wiki/File:Vbl-erased.png
.. |image8| image:: /maptool/images/thumb/d/df/Vbl-polyline-wall.png/300px-Vbl-polyline-wall.png
   :class: thumbimage
   :width: 300px
   :height: 223px
   :target: /rptools/wiki/File:Vbl-polyline-wall.png
.. |image9| image:: /maptool/images/thumb/1/1e/Vbl-drawx.png/300px-Vbl-drawx.png
   :class: thumbimage
   :width: 300px
   :height: 223px
   :target: /rptools/wiki/File:Vbl-drawx.png
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
