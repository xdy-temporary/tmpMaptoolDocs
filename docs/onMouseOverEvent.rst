=============================
onMouseOverEvent - MapToolDoc
=============================

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

   .. rubric:: onMouseOverEvent
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

         **This is a FAKE event**. You will need to create a macro and
         turn on some settings in Maptool to emulate this.

         This event can be simulated by turning on *"Show stat sheet on
         mouse over"* in the `MapTool
         Preferences </rptools/wiki/MapTool_Preferences#Tokens>`__:

         ::

               menu--> edit --> preferences --> Interactions --> 'Tokens' box: at the bottom --> check the checkbox

         And then creating a macro as a `campaign
         property </rptools/wiki/Introduction_to_Properties>`__ e.g.:

         ::

               *onMouseOverOnceVar:[macro("onMouseOver@lib:onMouseOver"):currentToken()]

         If you create a lib token ``lib:onMouseOver`` with the (self
         created) macro ``onMouseOver()`` then this macro will be called
         EVERY time you hover your mouse over a token.

         Note that this is extremely tricky and can result in system
         crashes or lock-ups if done incorrectly. The point is that the
         macro is called continuously when you hover over the token, so
         you have to take that into account when creating the macro.

         You can download a drop-in here
         `[1] <http://forums.rptools.net/viewtopic.php?f=46&t=18542>`__
         (if the link directs you to the 'forbidden' page then right
         mouse click on link and copy link location and paste that in
         the browser) that shows two methods that use this event. One
         method will run only once, this can be used e.g. to setup a
         token after you dragged it onto the map. The other method will
         run every time you hover over a token (but not continuously)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=onMouseOverEvent&oldid=5889"

