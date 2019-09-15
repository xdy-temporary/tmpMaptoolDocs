==========================
Trusted Macro - MapToolDoc
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

   .. rubric:: Trusted Macro
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
         from\ `Macros:TrustedMacros </maptool/index.php?title=Macros:TrustedMacros&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         A Trusted Macro is a macro that fits certain criteria, allowing
         it access to
         `functions <Category:Macro_Function>`__ and `roll
         options <Category:Roll_Option>`__ that are
         protected from normal use.

         `Functions <Category:Macro_Function>`__ and `roll
         options <Category:Roll_Option>`__ that require a
         Trusted Macro will have the following note on their article:

         .. container::

             Note: This function can only be used in a **Trusted Macro**

         Some parameters are only usable within a Trusted Macro, they
         will have the following note on their description:

         .. container:: template_trusted_param

             Note: This parameter can only be used in a **Trusted
            Macro**. 

         In order for a macro to be trusted it must adhere to three
         requirements. **If a macro is typed into the chat window, and
         not attached to a macro button, the only requirement is that
         the GM is the person who typed the macro.**

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 First Requirement <#First_Requirement>`__
            -  `2 Second Requirement <#Second_Requirement>`__
            -  `3 Third Requirement <#Third_Requirement>`__
            -  `4 Why trusted macros? <#Why_trusted_macros.3F>`__
            -  `5 A macro is trusted when
               ... <#A_macro_is_trusted_when_...>`__

         .. rubric:: First Requirement
            :name: first-requirement

         A trusted macro must not be editable by players. Allowing
         players to edit trusted macros is tantamount to making all of
         their macros trusted. To make it so players cannot edit a
         macro, you must uncheck the Allow Players to Edit Macro
         checkbox on the Options tab of the macro window. This setting
         defaults to being checked, allowing players access to edit any
         macro. As of 1.3b54 the default can be changed in the
         Preferences.

         .. container:: center

            .. container:: thumb tnone

               .. container:: thumbinner

                  |image0|

                  .. container:: thumbcaption

                     View of the Macro Options tab.

         .. rubric:: Second Requirement
            :name: second-requirement

         A trusted macro must not call another macro that is not
         trusted, any such call will cause the originating macro be
         considered an untrusted macro.

         .. rubric:: Third Requirement
            :name: third-requirement

         After satisfying the first and second requirements, the third
         requirement can be satisfied in two ways:

         -  Clicking the macro button as a GM.
         -  Placing the macro on a `library
            token <Library_Token>`__ and having a player
            call it using a `roll
            option <Category:Roll_Option>`__ or `macro
            link <macroLink>`__.

         .. rubric:: Why trusted macros?
            :name: why-trusted-macros

         Using trusted macros can, for example, allow gamemasters to set
         up macros on `library tokens <Library_Token>`__
         that can be called by players, but edited only by GMs, and
         which can access functions that players would not normally be
         able to access. Such macros can use trusted-only options or
         functions (such as the
         `[token():] <token_(roll_option)>`__ roll option
         or the `switchToken() <switchToken>`__ function)
         to modify or read values from NPC tokens that players do not
         own.

         .. rubric:: A macro is trusted when ...
            :name: a-macro-is-trusted-when-...

         ::

             * Anything the GM types into the input box is trusted

         ::

             * Anything a non GM types into the input box is not trusted.

         ::

             * Any auto execute macro that is non player editable is trusted.

         ::

             * Any auto execute macro that is player editable is not trusted.

         ::

             * Any non auto execute macro gets copied into the input box to be edited, so results in one of the first two rules

         *quoted
         Craig(\ *\ `[1] <http://forums.rptools.net/memberlist.php?mode=viewprofile&u=1338>`__\ *)*

         Lets test macros under certain combinations of macro location,
         player or gm, auto-execution and if it is player-editable or
         not. The test was performed using
         `isTrusted() <isTrusted>`__ and the campaign
         macro was "applied to token".

         ============== ========== ============ =============== ==========
         Macro location clicked by auto-execute player-editable is trusted
         ============== ========== ============ =============== ==========
         campaign       GM         •            •               ✓
         campaign       GM         •            -               ✓
         campaign       GM         -            •               ✓
         campaign       GM         -            -               ✓
         lib:token      GM         •            •               -
         lib:token      GM         •            -               ✓
         lib:token      GM         -            •               ✓
         lib:token      GM         -            -               ✓
         pc token       GM         •            •               -
         pc token       GM         •            -               ✓
         pc token       GM         -            •               ✓
         pc token       GM         -            -               ✓
         campaign       player     •            • \*            ✓
         campaign       player     •            -               ✓
         campaign       player     -            •               -
         campaign       player     -            -               -
         pc token       player     •            •               -
         pc token       player     •            -               ✓
         pc token       player     -            •               -
         pc token       player     -            -               -
         ============== ========== ============ =============== ==========

         *\*: This is actually not editable by the player since its a
         campaign macro.*

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Trusted_Macro&oldid=5499"

