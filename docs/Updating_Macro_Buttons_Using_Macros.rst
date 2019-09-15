================================================
Updating Macro Buttons Using Macros - MapToolDoc
================================================

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

   .. rubric:: Updating Macro Buttons Using Macros
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

         .. rubric:: Dynamically Updating a Token's Macro Buttons
            :name: dynamically-updating-a-tokens-macro-buttons

         Some times you want to modify what a
         `Token <Token>`__'s `macro
         button <Macro_Button>`__ from within a macro,
         this could be to visually represent a spell or power as having
         been used or even indicating that it is available for use.

         A quick note on some of these examples, before 1.3b51 it is
         only possible to have 2 levels deep of code: blocks, so some of
         the examples do things a little differently than you would if
         you could have multiple levels of code: blocks to avoid running
         into the problem. Also before 1.3b50 there is no way to get the
         index of the button that has been pressed, these tutorials show
         you how to "guess" the button that is pressed. As of 1.3b50 you
         can use the function
         `getMacroButtonIndex() <getMacroButtonIndex>`__
         to determine exactly which macro button has been clicked on the
         token.

         This tutorial is broken into several parts, although DnD4e is
         used to explain the concepts they are just as valid for any
         other system where you want to track if a skill has already
         been used or not.

         -  `Updating Macro Buttons Using a Macro (Prefix
            Method) <Updating_Macro_Buttons_Using_a_Macro_(Prefix_Method)>`__
         -  `Updating Macro Buttons Using a Macro (Group
            Method) <Updating_Macro_Buttons_Using_a_Macro_(Group_Method)>`__
         -  `Updating Macro Buttons Using a Macro (Label
            Method) <Updating_Macro_Buttons_Using_a_Macro_(Label_Method)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Updating_Macro_Buttons_Using_Macros&oldid=5552"

