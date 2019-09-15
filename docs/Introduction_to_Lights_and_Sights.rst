==============================================
Introduction to Lights and Sights - MapToolDoc
==============================================

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

   .. rubric:: Introduction to Lights and Sights
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
             • \ `español <Introduction_to_Lights_and_Sights/es>`__\  • \ `français <Introduction_to_Lights_and_Sights/fr>`__\ 
             • \ `日本語 <Introduction_to_Lights_and_Sights/ja>`__\ 

         .. container:: template_beginner

            | BEGINNER
            | THIS IS A BEGINNER ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 What are Sight, Light <#What_are_Sight.2C_Light>`__

               -  `1.1 Sight <#Sight>`__
               -  `1.2 Light <#Light>`__
               -  `1.3 Fog of War <#Fog_of_War>`__

            -  `2 The Sample Dungeon <#The_Sample_Dungeon>`__
            -  `3 Configuring Sight Types and Light
               Sources <#Configuring_Sight_Types_and_Light_Sources>`__

               -  `3.1 Sight Types <#Sight_Types>`__

                  -  `3.1.1 Sight Type
                     Limitations <#Sight_Type_Limitations>`__

               -  `3.2 Light Sources <#Light_Sources>`__

                  -  `3.2.1 Groups <#Groups>`__
                  -  `3.2.2 Light Source
                     Syntax <#Light_Source_Syntax>`__

               -  `3.3 Giving Tokens and Objects Sight and
                  Light <#Giving_Tokens_and_Objects_Sight_and_Light>`__

            -  `4 Vision Modes <#Vision_Modes>`__

               -  `4.1 Off <#Off>`__
               -  `4.2 Day <#Day>`__
               -  `4.3 Night <#Night>`__
               -  `4.4 Vision Modes and Fog of
                  War <#Vision_Modes_and_Fog_of_War>`__

            -  `5 Using Sight and Light in a
               Game <#Using_Sight_and_Light_in_a_Game>`__

               -  `5.1 Vision Range <#Vision_Range>`__

            -  `6 Vision Modes and Sight <#Vision_Modes_and_Sight>`__

               -  `6.1 Sight when Vision is
                  "Off" <#Sight_when_Vision_is_.22Off.22>`__
               -  `6.2 Sight when Vision is
                  "Day" <#Sight_when_Vision_is_.22Day.22>`__
               -  `6.3 Sight when Vision is
                  "Night" <#Sight_when_Vision_is_.22Night.22>`__

         .. rubric:: What are Sight, Light
            :name: what-are-sight-light

         MapTool offers three features that help to simulate the idea
         that when a character is adventuring in an environment, they
         are not always granted an "ominiscient view" of the entire area
         - they can't see through walls, around corners, or into the
         depths of dark dungeons. This is a difficult thing to simulate
         when playing face to face, but with a computer, it becomes
         possible to restrict a character's vision to what they might
         actually see - thus raising the tension and possibly the
         immersion of the game. The three features that MapTool offers
         are **Sight**, **Light**, and **Fog of War**.

         .. rubric:: Sight
            :name: sight

         Sight is the ability for a
         `token <Token:token>`__ to "see" its surroundings
         - in this case, what a player's token can "see" becomes visible
         to the player on their instance of MapTool (the GM can always
         see everything on the map; players, on the other hand, can be
         limited in what they see by things like `Vision Blocking
         Layers <Introduction_to_Vision_Blocking>`__,
         light, and `Fog of
         War </maptool/index.php?title=Introduction_to_Fog_of_War&action=edit&redlink=1>`__).
         This makes for a more immersive game, as players will wonder
         "What's around that corner?" and, "I hope my torch doesn't burn
         out...it's dark in this dungeon!"

         .. rubric:: Light
            :name: light

         Light is a feature that allows tokens and objects to cast
         "light" over a certain area, illuminating it. This means that
         in a dark dungeon, torches on the walls can illuminate small
         areas of the dungeon (removing/erasing any Fog of War that
         might cover that area) and be seen by the players (in other
         words, the area illuminated by the light source becomes visible
         to the players, assuming that the player's token has sight, and
         there is no VBL in the way).

         Light is critical when a map is using "Night" mode for vision,
         since without light, a token is stuck in the pitch black!

         .. rubric:: Fog of War
            :name: fog-of-war

         Fog of War is a system that represents what a token has seen as
         it is moved about the Map, and what part of the map or
         environment the token can directly see at that time. Fog of War
         should **not** be confused with shadows or darkness. You can
         have Fog of War on a Map that has no light or vision mode
         active at all.

         When a token with sight "sees" into an area of Fog of War, the
         Fog is erased, letting the player see the map that was hidden
         beneath the opaque Fog of War. When an area that a token *has*
         seen is no longer *directly* visible to the token, the opaque
         Fog of War (the "Hard Fog") is replaced by a semitransparent
         Fog (called "Soft Fog"). This is a visual reminder that the
         player *has* seen that area, but cannot see it *right now.* Any
         token in the Soft Fog is hidden from the character just as if
         it were in Hard Fog.

         **Remember**: *Fog of War simply indicates what area of the
         maps have been directly seen by a token.*

         Fog of War is a sufficiently complex discussion on its own that
         - even though it is intimately connected with light and sight -
         it deserves its own brief, but separate, tutorial. Check out
         `Introduction to Fog of
         War </maptool/index.php?title=Introduction_to_Fog_of_War&action=edit&redlink=1>`__
         to get details and screenshots on using Fog of War in your
         games.

         .. rubric:: The Sample Dungeon
            :name: the-sample-dungeon

         .. container:: thumb tright

            .. container:: thumbinner

               |image0|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:samp-dungeon.png>`__

                  The sample dungeon map used in this tutorial.

         A sample dungeon is used for all of the screenshots and
         examples in this tutorial (and in the `Introduction to Vision
         Blocking <Introduction_to_Vision_Blocking>`__). A
         screenshot of the sample dungeon is shown at right; you can
         also download the Campaign File for this dungeon
         `here </maptool/index.php?title=here&action=edit&redlink=1>`__.

         .. rubric:: Configuring Sight Types and Light Sources
            :name: configuring-sight-types-and-light-sources

         Both Sight Types and Light Sources are configured from the
         Campaign Properties window, under the Sight and Light tabs. To
         open the Campaign Properties dialog, go to **Edit > Campaign
         Properties.**

         .. rubric:: Sight Types
            :name: sight-types

         .. container:: thumb tright

            .. container:: thumbinner

               |image1|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:cprops-sighttab.png>`__

                  The Sight tab in the Campaign Properties dialog

         The Sight Types tab lets you set up different kinds of "sight"
         (such as low-light, or darkvision/infrared, or normal vision,
         and so forth). MapTool has some default sight types set up when
         you first open it. If you look at the sight tab, you'll see the
         following:

         ::

            Conic Vision: cone arc=120 
            Normal Vision - Short Range: circle distance=10.0 
            Lowlight: circle x2 
            Darkvision: circle r60 
            Square Vision: square 
            Normal: circle 

         Each of those items defines a **Sight Type**. The sight type is
         defined using a specific syntax, explained in the Campaign
         Properties window. The most basic one is simply a shape, as in:

         ::

            Normal: circle

         This simply says that "normal sight is circular." There is no
         limit to the range except the vision distance set on the *Map
         itself*, which defaults to 1,000 units. You can set e.g.
         distance=10 to limit the sight, this can reflect a thick fog
         for example where the players wade through.

         A more complex entry is the one for "Lowlight" sight:

         ::

            Lowlight: circle x2

         In this case, the vision name is **Lowlight**, and the shape is
         circular. However, an additional option was added on the end -
         *x2*. This is an option that interacts with *light sources*,
         multiplying their effective radius by 2 for any token that has
         the Lowlight vision. So where a token with Normal vision might
         see 20 units when using a torch, a token with Lowlight vision
         can see *40* units.

         Looking at an even more complex entry, consider the one for
         "Darkvision":

         ::

            Darkvision: circle r60

         In this entry, there are four components.

         -  **Darkvision**: this is, of course, the *name* of the Sight
            Type (you could call it "Thermographic Vision" if you like).
            This name appears in the token configuration dialog when you
            want to activate token sight.
         -  **circle**: this signifies the shape of the visual area, in
            this case, indicating that the visual area is circular;
            we've seen this before.
         -  **r**: this is a code that signifies that this sight type
            has a "personal" light source - in other words, it is
            effectively a light source only *that token* can see. This
            is what makes this "darkvision," for instance - the token
            can see just fine in the dark, but that token's *allies*
            might be completely blind.
         -  **60**: this is the range of the sight type, starting from
            the center of the token's square, and counted in "map units"
            (so if your map is 5 units per cell, this will cover 12 map
            cells; if your map is 1 unit per square, this will cover 60
            squares). Note that since range is measured from the
            *center* of the square or hex, many users add a fractional
            amount to the range so that the end of the range lines up
            nicely with a hex or square boundary.

         **Tip:**\ you can use r0.5 in normal vision, this way when you
         turn on night mode, players that do not have a light source can
         at least still see there own token. This setting could look
         like: "Normal: circle r0.5", adding limited vision in the mix,
         this would become: "Normal Vision - Short Range: circle r0.5
         distance=10.0 "

         Configuring sight types is unique to the game being played, and
         so the specifics of it need to be left to the campaign
         designer. However, suffice it to say that Sight is a
         configurable option and offers a great deal of flexibility.

         .. rubric:: Sight Type Limitations
            :name: sight-type-limitations

         Flexible as it is, there are a few limitations on Token Sight.

         -  **One sight type at a time**: tokens can only have one kind
            of sight active at a time (a token cannot have Darkvision
            and Normal sight active simultaneously)
         -  **Sight has no color**: sight types do not have colors of
            their own. Any color visible to the players will be based on
            the color of the light source, not the sight type (there is
            one exception to this, however: in `MapTool
            Preferences <MapTool_Preferences>`__, you can
            opt to have the vision color of the token match its
            `Halo <token.halo>`__ color)

         .. rubric:: Light Sources
            :name: light-sources

         .. container:: thumb tright

            .. container:: thumbinner

               |image2|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Cprops-lighttab.png>`__

                  The Light tab in the Campaign Properties dialog.

         The Light tab provides an interface very similar to the Sight
         tab - a text window with a number of different items defined as
         a simple string of text. The default MapTool campaign
         properties show the following light sources:

         ::

            D20
            ----
            Candle - 5 : 5 10#000000 
            Lamp - 15 : 15 30#000000 
            Torch - 20 : 20 40#000000 
            Everburning - 20 : 20 40#000000 
            Lantern, Hooded - 30 : 30 60#000000 
            Sunrod - 30 : 30 60#000000 
            Generic
            ----
            5 : 5 
            15 : 15 
            20 : 20 
            30 : 30 
            40 : 40 
            60 : 60 

         .. rubric:: Groups
            :name: groups

         In the above default lights, there are two groups: D20 and
         Generic. A group is defined by typing its name, and placing
         beneath it four hyphens in a row: ``----``. Groups appear in
         the right-click menu on a token, and are basically a way for
         you, as GM, to organize the different light sources in your
         game.

         `Aura <Aura>`__ is not included by default and
         must be added manually.

         .. rubric:: Light Source Syntax
            :name: light-source-syntax

         Beneath each group header are a list of light sources. The
         syntax for these is very similar to the syntax for Sight Types,
         with a couple exceptions. Let's look at the entry for Sunrod:

         ::

            Sunrod - 30: 30 60#000000

         There are three elements shown here:

         -  **Sunrod - 30**: the name of the light source; this is what
            appears in the right-click menu on a token, under the
            appropriate Light Source group
         -  **30**: this is a light source radius of 30 units; the
            "first" radius of the light
         -  **60#000000**: this is a *second* radius to the light, and a
            hexadecimal color code.

            -  **Light Source Radii**: A light source can have one or
               more radii, each of which can be set to a different
               color. In the sunrod example, the first radius has no
               color (or rather, it has the default color of white,
               which means that the area it covers is completely
               illuminated). The second radius (60) has the color
               #000000, which, when rendered by MapTool, makes a "dim
               light" area (translucent gray) from 30 units to 60 units.
               The overall effect is that from the center of the light
               source out to 30 units, the light is "bright," and
               everything is fully illuminated. From 30 units to 60
               units, the light is a big darker, and items in that area
               are less brightly lit.

         One element is left out here, which is the light source
         *shape.* Like Sight Types, light sources can have shapes. The
         default shape is circular, and so if you do not specify a
         shape, the light source will default to circle-shaped. The
         other shapes are:

         -  **Cone**: create a conic area with a user-defined arc. This
            projects the light along the current facing of the token.
         -  **Square**: this creates a square light area
         -  `Aura <Aura>`__: this is a special light
            source, because while it is blocked by VBL and can cast
            colored light, it does not actually illuminate anything
            (therefore, an `aura <aura>`__ will not reveal
            hidden areas to a player, but it does act as a way to see
            how far from a token its aura extends).

         .. rubric:: Giving Tokens and Objects Sight and Light
            :name: giving-tokens-and-objects-sight-and-light

         .. container:: thumb tright

            .. container:: thumbinner

               |image3|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Token-config-sight.png>`__

                  Set the "Has Sight" checkbox to give a token a sight
                  type.

         .. container:: thumb tright

            .. container:: thumbinner

               |image4|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Token-config-light.png>`__

                  Use the right-click menu for the token to select a
                  Light Source.

         To give a token Sight and Light, do the following:

         #. Double-click on the token and go to the Config tab. There,
            check the Has Sight box, and select the appropriate sight
            type. Remember that a token can only have one type of sight
            active at a time.
         #. Click **OK** to save the sight settings.
         #. Right-click on the token, and go to Light Source. Navigate
            through the submenus until you can select a specific light
            source. The token now has a light source.

         .. rubric:: Vision Modes
            :name: vision-modes

         .. container:: thumb tright

            .. container:: thumbinner

               |image5|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Map-vision-mode.png>`__

                  Setting the vision mode on a map.

         Recent builds of MapTool introduced the concept of Vision
         Modes, which let the GM dictate how vision and light will
         affect a given map. There are three Vision Modes: **Off**,
         **Day**, and **Night**, each of which alters the way in which
         light and vision interact for a token.

         In the following discussion of vision modes, what is visible to
         the player as they move their token is based on what is visible
         to the *token itself*. Thus, if, under the proper settings, an
         enemy token is visible to the player's token, the player will
         see it on the Map. However, if that enemy token is *not*
         visible to the player's *token*, it will not appear on the
         player's instance of MapTool.

         .. rubric:: Off
            :name: off

         When Map Vision is set to "Off," Token vision settings are not
         taken into account when displaying information to players: all
         things are visible at all times, unless hidden beneath Fog of
         War.

         .. rubric:: Day
            :name: day

         In Day mode, light sources are not considered when evaluating
         token vision and what lies inside the tokens visual range.
         Furthermore, no part of the map is hidden from the players
         (that is, they will see the entire map - not necessarily all
         the *tokens* on a map, but they will see the layout of the
         entire dungeon, building, or area). Effectively, the Day mode
         assumes that a bright sun is shining down on everything,
         illuminating it all, and everything is visible unless blocked
         by VBL or covered by Fog of War.

         .. rubric:: Night
            :name: night

         This mode incorporates Light Sources into the calculations,
         effectively assuming that it is "night" in the game, and that
         without a light source, the tokens are in a pitch-black
         environment and can see nothing. If Fog of War is used with
         Night Mode, light sources will reveal areas covered by Fog of
         War, assuming a token can see the light source and the area is
         not blocked by VBL.

         .. rubric:: Vision Modes and Fog of War
            :name: vision-modes-and-fog-of-war

         You can use Fog of War with any of the Vision modes: Off, Day,
         or Night.

         -  When Map Vision is Off, Fog is removed to the extent of the
            token's sight (set using the Token Properties dialog). Soft
            Fog does not appear when using Off Mode, as tokens do not
            actually "see" anything in this mode. VBL works normally.
         -  In Day Mode, the Fog will be removed out to the limit of the
            token's visual range (which, if you note when you create a
            map, defaults to 1,000 units), and token vision is blocked
            by VBL. In this mode, Fog of War has both Hard and Soft Fog,
            as token vision is active.
         -  In Night Mode, Fog of War (when removed) is cleared to the
            maximum radius of a token's light source (remember, though -
            the token must a) have sight, and b) have a light source -
            without a light source, the token can't see at all!). Thus,
            when using Fog of War and Night mode for vision, the fog
            will be removed only where the light source illuminates it.
            Soft Fog works in this mode just as it works in Day mode.

         .. rubric:: Using Sight and Light in a Game
            :name: using-sight-and-light-in-a-game

         Sight, Light, and Fog interact in a number of ways in-play. To
         start, let's look at using Sight without Light or Fog of War.
         The examples below will use the sample dungeon shown to the
         right. Note that the sample dungeon uses `Vision
         Blocking <Introduction_to_Vision_Blocking>`__, a
         feature of MapTool that blocks the line of sight of a token
         (meaning you can use it to indicate the placement of walls,
         pillars, and similar objects that would obstruct a character's
         vision).

         .. rubric:: Vision Range
            :name: vision-range

         .. container:: thumb tright

            .. container:: thumbinner

               |image6|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-sight-boundary.png>`__

                  MapTool shows a white boundary illustrating the limit
                  of the token's visual range.

         .. container:: thumb tright

            .. container:: thumbinner

               |image7|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-sight-boundvbl.png>`__

                  When the token with sight is on a map with
                  `VBL <Introduction_to_Vision_Blocking>`__,
                  the token's sight boundary follows the VBL.

         When you configure a token to have sight, when you hover your
         mouse token over the token, MapTool will illustrate the limit
         of the token's visual range with a white border (a circle if
         the sight type is circular, or square if square, or a cone if
         it's cone shaped, etc.). The screenshot to the right shows a PC
         token with the sight type "Normal - Short Range" configured.
         Note the white circle indicating the boundary of the token's
         vision.

         In the first screenshot to the right, there is no VBL on the
         map, so the token's visual range is unaffected. For a more
         practical illustration of the "line of sight" boundary,
         consider the second screenshot, taken using the same token, but
         on the dungeon map, which employs VBL along the the walls of
         the dungeon. If you look closely, you'll see the white boundary
         - however, instead of being circular, it is blocked in certain
         areas by the VBL of the map, and thus has an irregular shape.

         .. rubric:: Vision Modes and Sight
            :name: vision-modes-and-sight

         As mentioned above, there are three vision modes - **Off**,
         **Day**, and **Night**. Each setting affects how token vision
         is evaluated by MapTool.

         .. rubric:: Sight when Vision is "Off"
            :name: sight-when-vision-is-off

         .. container:: thumb tright

            .. container:: thumbinner

               |image8|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionoff-gmview.png>`__

                  The GM's view of a map with no vision. Note that if
                  the map has VBL on it, the white boundary of token
                  sight range will appear, but it's not actually used to
                  determine what is visible - since vision is disabled.

         .. container:: thumb tright

            .. container:: thumbinner

               |image9|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionoff-plyrview.png>`__

                  The Player's view of the same map.

         When Vision is set to **Off**, the token's sight settings are
         not taken into account when deciding what to display to the
         player. Instead, the player can look at all of the items and
         backgrounds on the map. VBL will still block the "visual
         boundary", but it won't actually block vision in any way -
         something on the far side of VBL from a token is still visible
         on the player's screen.

         The two screenshots to the right illustrate this: the top
         screenshot is the GM's view of the screen, while the shot on
         the bottom is the Player's view of the same map - note that
         they both see the same items. The only items a player will not
         see are those items on the Hidden layer, or those items that
         the GM has explicitly flagged as invisible to players.

         .. rubric:: Sight when Vision is "Day"
            :name: sight-when-vision-is-day

         .. container:: thumb tright

            .. container:: thumbinner

               |image10|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionday-gmview.png>`__

                  GM's view of a map with Vision set to *Day* mode.

         .. container:: thumb tright

            .. container:: thumbinner

               |image11|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionday-plyrview.png>`__

                  Player's view of the same map. Note that the other
                  tokens that the GM can see are *not* visible to the
                  player, since VBL blocks them.

         When Vision is set to **Day**, the token's sight settings are
         take into account when determining what objects and other
         tokens are visible to the player. Light source settings are
         *not* taken into account. If an object or token lies outside
         the player's token's vision, it will not be visible to the
         player. Likewise, if an object or token lies beyond VBL from
         the player token, it will not be visible.

         The screenshots to the right show this (again, the top is the
         GM's view, and the bottom is the Player view). Note that in the
         player view, the Dragon and Hero token are not visible to the
         Elf token (the player token), because they are hidden by VBL.

         .. rubric:: Sight when Vision is "Night"
            :name: sight-when-vision-is-night

         .. container:: thumb tright

            .. container:: thumbinner

               |image12|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionnight-gmview.png>`__

                  GM's view of a Map with vision set to Night mode.

         .. container:: thumb tright

            .. container:: thumbinner

               |image13|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionnight-plyrview.png>`__

                  Player's view of the same map - note that the Elf
                  token (the player's token) is not visible, because the
                  Elf has no light source!

         .. container:: thumb tright

            .. container:: thumbinner

               |image14|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` <File:Nofog-visionnight-plyrview-candle.png>`__

                  The player's Elf token is now visible, because it has
                  a light source.

         When vision is set to **Night**, both the token's sight
         settings *and* the token's light source setting is taken into
         account when determining what the token is able to see. If a
         token lacks a light source, it will be unable to see anything
         unless it has a sight type that indicates *personal light* (in
         other words, a sight type like the "Darkvision" type discussed
         previously) - in fact, the token itself will not be visible to
         the player!

         The screenshots to the right show Night-mode vision in effect.
         The top screenshot is the GM view; the second two show the
         Player view *without* a light source on the player's Elf token,
         and then with the "Candle - 5" light source selected. There are
         several things to note about this:

         #. "Night" mode vision does not add "darkness" to the map in
            any visual way - it simply means that without a light
            source, tokens cannot see other tokens, objects, or
            themselves.
         #. In the first Player screenshot, the player's Elf token is
            not visible in the lower left room of the dungeon - that's
            because the player's token doesn't have a light source, so
            it can't see - and therefore, the *player* can't see
            anything but the map background.
         #. In the second Player screenshot, the Elf is now visible
            because it has a light source active. This light source
            means that the player can see out to the limit of its light
            source's area.

         .. container:: template_languages

            Languages:  English
             • \ `español <Introduction_to_Lights_and_Sights/es>`__\  • \ `français <Introduction_to_Lights_and_Sights/fr>`__\ 
             • \ `日本語 <Introduction_to_Lights_and_Sights/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Lights_and_Sights&oldid=4335"

