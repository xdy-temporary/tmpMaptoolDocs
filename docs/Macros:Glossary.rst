=====================
Glossary - MapToolDoc
=====================

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

   .. rubric:: Glossary
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
         from\ `Macros:Glossary </maptool/index.php?title=Macros:Glossary&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: B
            :name: b

         Bar
            One, two, or multi-image graphical elements displayed on a
            token used to indicate the status of a consumable resource
            such as Hit Points.

         .. rubric:: C
            :name: c

         Campaign or Campaign file
            A zipped XML file with the **.cmpgn** file extension
            containing tokens, maps, token macros, campaign macros,
            campaign properties, and `token
            properties <Token_Property>`__

         Campaign Macro
            A macro specific to a campaign file. These macros are
            available to players and the GM, and are displayed in the
            Campaign Macros window.

         .. rubric:: D
            :name: d

         Dialog
            A modeless (*i.e.*, does not require user interaction) popup
            generated by the
            `dialog <Tutorials:Macros:DialogsAndFramesIntro>`__
            roll option.

         .. rubric:: F
            :name: f

         Frame
            A dockable MapTool window that can be generated via the
            `frame <Tutorials:Macros:DialogsAndFramesIntro>`__
            roll option.

         .. rubric:: G
            :name: g

         Global Macro
            Macros that are available regardless of the campaign file
            currently loaded in MapTool, and regardless of whether the
            instance of MapTool is a server or a client. Global macros
            are *only* available to the running instance.

         .. rubric:: H
            :name: h

         Halo
            A colored border that appears around a token on the map. The
            Halo can be set via the right-click menu to one of several
            pre-set colors, or set and changed via macro by changing the
            variable `token.halo <token.halo>`__.

         .. rubric:: I
            :name: i

         Image token
            A special token that contains an image that may be
            referenced by other macros.

         Initiative Panel
            A dockable panel in MapTool that provides simple initiative
            tracking functionality.

         .. rubric:: L
            :name: l

         Library Token
            A special token designed to hold a library of macros
            (similar to a function library) that can be called by token
            macros, campaign macros, and global macros. Often called
            "Lib:tokens."

         .. rubric:: M
            :name: m

         Macro
            A series of text instructions used to automate processes in
            MapTool. See `Macro
            Introduction <Macros:introduction>`__ for more
            details.

         Map
            An image file displayed in the map display area in MapTool.
            This image is shared among all connected players and the GM.

         .. rubric:: P
            :name: p

         Pion
            Marqueur visuel représentant habituellement un personnage,
            un PNJ ou un monstre.

         Property
            Generic term for a variable contained in a token; a more
            explicit term is `Token
            Property <Token_Property>`__.

         .. rubric:: R
            :name: r

         Resource Library
            The library of images, tokens, and other resources that
            MapTool can access. The Resource Library appears as a set of
            folders in the Library window in MapTool's main interface.
            These folders are links that point to locations on your
            computer's hard drive - if you add a folder to the resource
            library, MapTool becomes aware of that folder's contents,
            and they can be dragged from the Library window onto a
            MapTool map, or selected via several different dialogs.

         Roll Option
            One of several "switches" that alter how the macro code
            following the switch is executed. Roll options (also called
            roll formatting options) are always in the format
            [option(*arguments*): *body of roll*]. Simple options
            include `[h: ] <Macros:Roll:types>`__ (hides
            output of roll) or `[t:
            ] <Macros:Roll:types>`__ (creates a "tooltip
            roll"), while more complex options include `[SWITCH():
            ] <Macros:Branching_and_Looping>`__ and
            `[IF(): ] <Macros:Branching_and_Looping>`__.

         .. rubric:: S
            :name: s

         State
            Also called a `token state <Token:state>`__, a
            state is a binary condition that is set for a given token.

         String List
            A string containing a list of items in the format "item1,
            item2, item3,..."

         String Property List
            A string containing key-value pairs in the format
            "key1=value1; key2=value2; key3=value3;..."

         .. rubric:: T
            :name: t

         Token
            A visual marker that is dropped on a MapTool map. Tokens
            usually represent characters, monsters, or NPCs, and often
            including an image as well as a set of `token
            properties <Token_Property>`__ which define
            the attributes of the creature or character.

         Token Bar
            One, two, or multi-image graphical elements displayed on a
            token that are typically used to visually indicate the
            status of consumable or expendable resource such as Hit
            Points or Ammunition.

         Token Id
            A string that uniquely identifies a specific token. Many
            macro functions operate on the current token by default but
            allow a **token id** to be given so that operations are
            applied against that token instead. When a token id is
            provided MapTool checks the string against (1) the token
            name, (2) the token's '**GM Name'**, and (3) the internal
            identifier for the token. The first two are
            self-explanatory, but the third one is not normally visible
            anywhere within MapTool. Token ids can be obtained by
            calling `getTokens <getTokens>`__, for
            example, and will appear as a long string of uppercase
            letters and digits.

         Token State
            A binary (i.e., it has two possible values, 1 or 0) variable
            that is set for a given token, frequently used for
            conditions or statuses that affect a particular character in
            a game (for example "Bloodied" or "Fatigued"). Token states
            often have images associated with them that appear as
            overlays on the token.

         Trusted Macro
            A macro run from a Library token or run by the GM, that
            cannot be edited by a player.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Glossary&oldid=3995"

