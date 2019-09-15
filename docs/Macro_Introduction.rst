===============================
Macro Introduction - MapToolDoc
===============================

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

   .. rubric:: Macro Introduction
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

         .. container:: template_note

            **This article has been flagged for removal! If you have any
            objections, speak up now.
            **
            | This URL will be forwarded to `Introduction to Macro
              Writing </rptools/wiki/Introduction_to_Macro_Writing>`__
              upon removal.

            Removal date set for: 04.21.2009

         Welcome to the Macro Documentation page for **MapTool**, from
         the **RPTools.net** developers!

         Macros are a way of automating tasks within MapTool. They can
         be attached to tokens, allowing any owner of the token to
         execute them via a right-click context menu or via the various
         panels available from the **Window** menu. (Actually, the
         macros can be edited by any owner of the token or by the GM, if
         MapTool is running as a server.)

         There are also two other categories of macros that are not
         attached to tokens: global and campaign. Be aware that if these
         macros are going to access properties on a token, the token
         must be identified somehow. The two common approaches are to
         apply the macro against the *currently selected tokens* or for
         the macro to be written such that it prompts for the *user to
         select a token*. The only other difference between the two
         categories is that global macros are stored on the local
         computer under your username and will exist in any campaign
         that you connect to (as a client) or any campaign you load (as
         a server). The campaign macros, as their name implies, are
         saved as part of the campaign and will not be available when
         **MapTool** is not accessing that campaign (as either client or
         server). In addition, campaign macros are sent to clients when
         they connect to a **MapTool** server so that they can be used
         on the client as well.

         The **MapTool** macros should be supported for quite some time,
         but the reader should be aware that as **MapTool** transitions
         from a Java 5 application to Java 6, there is a stated goal of
         using Javascript as the macro language instead of these "home
         built" macros. There are a lot of reasons for this, but suffice
         to say that when Javascript becomes the macro language of
         choice, it is unlikely that these macros will see much further
         development or even bug fixes. However, **MapTool** is open
         source software so anyone moderately competent in Java will be
         able to download the source code and make enhancements
         themselves, if necessary.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Macro Creation <#Macro_Creation>`__

               -  `1.1 Global Macros <#Global_Macros>`__
               -  `1.2 Campaign Macros <#Campaign_Macros>`__
               -  `1.3 Token Macros <#Token_Macros>`__

         .. rubric:: Macro Creation
            :name: macro-creation

         Macros can be created in a number of ways. In each case, the
         process is essentially the same although the details might
         vary: open a dialog window that allows access to the macro
         text, add or edit the macro text, save it when finished.
         Because **MapTool** macros have been evolving over time, there
         are multiple ways to edit token macros, but only a single
         technique used for both global and campaign macros. So we'll
         start with those last two and cover token macros last.

         .. rubric:: Global Macros
            :name: global-macros

         These are macros created by right-clicking in the **Global**
         panel that can be turned on or off via the **Window** menu in
         **MapTool**. These macros are stored under your username on the
         computer in a platform-dependent way by the Java runtime
         environment. For example, on the Microsoft Windows platform
         they are stored in the registry. On the Apple OSX platform they
         are stored under the user's **Library/Preferences** directory,
         and on other Unix systems they are written to an XML file under
         the user's **.java/.userPrefs** directory.

         As mentioned above, global macros are available regardless of
         when the **MapTool** instance is a client or server. They are
         not shared with other players who may be connected to a
         **MapTool** server. Because they are not shared, they are often
         used by GMs to implement functions they don't want the players
         to know about, such as random chances for an encounter or the
         choice of which PC is targeted by a random trap being sprung.

         These macros must provide some way to identify the token they
         should use for property values, if they are going to use any at
         all, so the **Apply to selected tokens** checkbox is often
         turned on when the macro is created.

         .. rubric:: Campaign Macros
            :name: campaign-macros

         These are macros created by right-clicking in the **Campaign**
         panel that can be turned on or off via the **Window** menu in
         **MapTool**. These macros are stored inside the campaign file
         that the GM creates. The contents of the campaign file, which
         includes these macros but also all images, are sent to all
         players when they connect to a **MapTool** server and select a
         map.

         Because campaign macros are sent to the clients, they are
         typically used in situations where the GM wants players to have
         access to a library of pre-written macros. These macros must
         provide some way to identify the token they should use for
         property values, so the **Apply to selected tokens** checkbox
         is often turned on when the macro is created.

         For example, the calculations for opposed skill checks might be
         placed here. The player would click on a button that executes a
         macro and the macro would retrieve the appropriate skill check
         modifiers from the selected token. It then makes the skill
         check, sending the numeric result only to the GM with the
         player receiving a message, "So-and-so rolls a skill check!"

         .. rubric:: Token Macros
            :name: token-macros

         These are the ones that most players will be familiar with.
         These macros are attached to tokens (**MapTool**
         representations of creatures, often including an image as well
         as a set of *properties* which define the attributes of the
         creature) which are owned by the player. The player may edit
         the macros themselves, allowing them to create customized
         commands that they can easily execute. These macros might
         access properties such as Strength or Dexterity, or information
         about weapons, or record damage and subsequent healing.

         (In the v1.3.b48 release of **MapTool**, there are now
         `"library tokens" </rptools/wiki/Token:library_token>`__. These
         are tokens that are accessible from any map within a campaign.
         The tokens themselves have names that start with **Lib:** and
         they represent "trusted" macro code. Only GMs may create tokens
         with such names or add them to maps, and the macros they
         contain can be referenced by players from their own macros.
         This allows the GM to write standard features once and then
         tell the players how to invoke those features from their own
         macros. These library tokens, or just **Lib:tokens** for short,
         can perform functions that player macros cannot, such as
         accessing or modifying the properties on tokens that the player
         does not own.)

         Token macros can be created, edited and accessed by clicking
         the corresponding macro button from the **Selection** or
         **Impersonated** panels (accessible from the application's
         **Window** menu).

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Macro_Introduction&oldid=6906"

