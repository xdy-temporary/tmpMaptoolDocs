=========================
Feature List - MapToolDoc
=========================

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

   .. rubric:: Feature List
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

            Languages:  `English <Shortcut_Keys>`__\ 
             • \ `日本語 <Shortcut_Keys/ja>`__\ 

         This list is compiled for Maptools version 1.3b86. If fairly
         extensive but still misses quite a lot of entries. It will
         however give you a good idea of what the capabilities are of
         Maptools.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Live and active
               community <#Live_and_active_community>`__
            -  `2 Fog of War <#Fog_of_War>`__
            -  `3 Maps <#Maps>`__
            -  `4 Grid <#Grid>`__
            -  `5 Library support <#Library_support>`__
            -  `6 Frameworks <#Frameworks>`__
            -  `7 Script language (Macro
               support) <#Script_language_.28Macro_support.29>`__
            -  `8 Tables <#Tables>`__
            -  `9 Preferences <#Preferences>`__
            -  `10 Interface <#Interface>`__
            -  `11 Tools <#Tools>`__
            -  `12 Different Languages <#Different_Languages>`__
            -  `13 Tokens <#Tokens>`__
            -  `14 Light <#Light>`__
            -  `15 Chat box <#Chat_box>`__
            -  `16 Maptool summarized in one
               picture <#Maptool_summarized_in_one_picture>`__
            -  `17 Drop-in: Bag of Tricks <#Drop-in:_Bag_of_Tricks>`__

         .. rubric:: Live and active community
            :name: live-and-active-community

         -  Maptool is supported by an active and lively community, this
            makes MT free, though your donation is always welcome
         -  MT is supported by a large Forum community
         -  MT is supported by an extensive set of Tutorial videos, in
            multiple languages
         -  MT is supported by a Wiki
         -  MT is Java based, meaning it plaform independent (e.g. runs
            on Window, Mac, Linux etc.)

         .. rubric:: Fog of War
            :name: fog-of-war

         -  Option for individual character fog of war, otherwise fow is
            shared by the entire party
         -  hard fog for undiscovered areas
         -  soft fog for previous discovered areas but outside LoS
            (note, no items on the token layer show to players if the
            item is in soft fog)
         -  option to reset the fog
         -  option to manually clear fog
         -  option to manually recreate fog
         -  option to have player movement clear fog automatically

         .. rubric:: Maps
            :name: maps

         -  Supports virtually infinite map, limited only by each
            connected computer's memory resources
         -  Support for creating maps
         -  Export and Import function for MT type maps
         -  Hi-res Screenshot support
         -  Ability to create maps real time (in game)
         -  Ability to drag and drop images into maptools that can be
            used as map
         -  Ability to drag and drop images into maptools that can be
            used as objects
         -  Support for 4 layers of map drawing:

            -  **background** here you either draw maps or drag external
               images as map. Both from outside maptools or from within
               maptools
            -  **object** here you can again draw and drag images both
               from outside MT or from the internal library
            -  **hidden** same as other layers but everything in this
               layer is visible to GM only
            -  **Token** the actual layer where players and GM have
               their tokens which they can move around. Same as other
               layers drawing and dragging support

         -  Multiple map support
         -  Texture support, for as well background as drawing

         .. rubric:: Grid
            :name: grid

         -  Different types of grids:

            -  Square
            -  Hex (Horizontal Hex)
            -  Vex (Vertical Hex)
            -  Isometric (as of 1.4)

         -  Grid color
         -  Grid size
         -  Grid offset
         -  Toggle snap to grid
         -  Grid is positioned above the background and below the
            objects to give a sense of depth in the maps
         -  Ability to auto-resize imported map images to quickly fit
            the grid (as of 1.4)

         .. rubric:: Library support
            :name: library-support

         -  MT a build in library with:

            -  Tokens (e.g. Hero, Dragon, Troll)
            -  Objects (e.g. door, wall, table)
            -  Textures (e.g. Grass, Cobble stones, Mud)
            -  States (e.g. Stunned, Blinded, Dazed)
            -  Other stuff like Overlays, a prepared Map, Health Bars,
               Dice, Cards

         -  Option to load (from the internet) other available resources
            like maps, tokens and objects
         -  Option to extend the resource library with material
            localized on your own PC

         .. rubric:: Frameworks
            :name: frameworks

         Through the maptools forum and its very lively community
         frameworks have been created which give support for the
         following RPG games

         -  D&D 3.5 Ed
         -  D&D 4 Ed (English, French and Spanish)
         -  D&D 5 Ed
         -  Pathfinder
         -  Warhammer 40k - Dark Heresy
         -  Warhammer 40k - Roque Trader
         -  Warhammer 40k - Deathwatch
         -  Warhammer 40k - Black Crusade
         -  Warhammer 40k - Only War
         -  Warhammer 2nd Ed
         -  Warhammer 3rd Ed
         -  Call of Cthulhu 5.6 Ed
         -  Call of Cthulhu 6 Ed
         -  Call of Cthulhu 7 Ed
         -  Fate 3.0
         -  Hackmaster
         -  Dragon Age
         -  Savage Worlds
         -  Hero 5th ed.
         -  HarnMaster 3
         -  Star Wars
         -  Bash
         -  Gurps
         -  Gumshoe
         -  Ars Magica 5h Ed.
         -  Dogs in the Vineyard
         -  A couple of bord games

         .. rubric:: Script language (Macro support)
            :name: script-language-macro-support

         -  MT provides a script language with which the above
            Frameworks have been developed
         -  There exists a acitve and up to date Wiki support for the
            script language
         -  There are several 'drop-in' resources available through the
            forum

         .. rubric:: Tables
            :name: tables

         -  Maptools provides a (rudimentary) support for tables
         -  Random results from the tables can be generated with the use
            of the script language

         .. rubric:: Preferences
            :name: preferences

         -  A LOT of settings are provided to personalize MT to your
            needs

         .. rubric:: Interface
            :name: interface

         -  Different panels are available

            -  Initiative Panel: contains images of the active tokens
               and there respective initiative number
            -  Global Panel: contains macros that are locally (on the
               PC) stored and are independent of the active Framework
               i.o.w. always there.
            -  Campaign Panel: contains macros that are applicable for
               the campaign (Framework)
            -  Selection Panel: contains macros specifically for the
               currently selected Token(s)
            -  Impersonate Panel: same as Selection only this always
               applies to a single Token
            -  Table Panel: Panel with the tables
            -  Resource Library Panel: here the Resources are available
            -  Map explorer Panel: here one can see which tokens are on
               the map and in which layer
            -  Draw explorer Panel: here one can see drawings by layer
               and edit their properties
            -  Connection Panel: shows who's connected through the
               (inter)net to your game

         -  Panels can be

            -  Docked or Undocked (floating)
            -  Hidden
            -  Auto-hidden, accordion style, ie, when you mouse near the
               edge where the panel is set to auto-hide, it pops out for
               use and hides itself once you mouse out.
            -  Docked panels may also be dragged into tabbed groups of
               multiple panels

         -  Full screen support
         -  Zoom option (which is definitely necessary with the very
            very very large maps

         .. rubric:: Tools
            :name: tools

         -  Force view
         -  Force Zoom Level
         -  Lock movement
         -  Lock Zoom

         .. rubric:: Different Languages
            :name: different-languages

         -  English
         -  French
         -  Italian
         -  Spanish
         -  German
         -  Polish
         -  Russian

         .. rubric:: Tokens
            :name: tokens

         -  Maptool differentiates between PC's and NPC's
         -  Option to set Ownership of tokens (so player can Own NPC
            tokens or multiple PCs)
         -  Option to set 'vision' of a token:

            -  Night vision
            -  Normal vision
            -  Arc/Cone, Circle, or Square
            -  Range

         -  Option to set 10 different sizes, among which free-size
            (technically, objects are "free size" and tokens are "native
            size")
         -  Local properties (like Strenght and Toughness) are
            completely customizable per token
         -  Stat sheet on mouse over token, again completely
            customizable (and can be hidden for all tokens)
         -  States can be set per token
         -  Health bars, either standard or again completely
            customizable (can also be used for e.g. Ammo, Stamina, etc.)
         -  Shape, different shapes are supported:

            -  Square
            -  Circle
            -  Top Down (rotates entire token when facing is set, token
               is also not limited to its square) (that last part
               applies to all tokens)

         -  Option to set token visibility (e.g. all clients can see or
            owners only)

         .. rubric:: Light
            :name: light

         -  set different ranges
         -  set different shapes (Square, Circle, Cone with an arc
            ranges from 1 to 360 degrees)
         -  set different colors
         -  set layers of lights (so first e.g. yellow and then an outer
            ring of e.g. red)
         -  set auras, don't shed light, but can be used for e.g. show
            ranges of weapons
         -  set auras visible to self, all, gm only
         -  Create different groups of light

         .. rubric:: Chat box
            :name: chat-box

         -  loads of chat commands
         -  smiley support
         -  can handle html commands
         -  broadcast option
         -  impersonate token and talk from that token
         -  whisper to a single token (so the rest won't see the
            message) or gm only
         -  (show/hide) typing notifications
         -  different colors
         -  scroll lock
         -  allow macro commands to be typed straight into the chat

         .. rubric:: Maptool summarized in one picture
            :name: maptool-summarized-in-one-picture

         |This is a combination of native Maptool functionality and a
         campaign (W40K) created in maptool.|

         .. rubric:: Drop-in: Bag of Tricks
            :name: drop-in-bag-of-tricks

         This is not a default feature which comes with Maptool, but
         something you need to install. This drop-in will roughly add an
         additional 80 features, like Teleports, animated doors,
         automatic VBL manipulation, token grouping, extended tables,
         debug tools, etc. etc. It can be found
         `here <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__.
         The web-post includes a full list of all features, tutorials on
         how to use and install it.
         --`Wolph42 <User:Wolph42>`__ 15:18, 11 May 2011
         (UTC)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Feature_List&oldid=7617"

