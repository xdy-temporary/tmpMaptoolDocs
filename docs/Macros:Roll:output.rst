===============================
Macros:Roll:output - MapToolDoc
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

   .. rubric:: Macros:Roll:output
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

            -  `1 Roll Visibility Options <#Roll_Visibility_Options>`__

               -  `1.1 Output Visibility <#Output_Visibility>`__
               -  `1.2 Tooltip Visibility <#Tooltip_Visibility>`__

            -  `2 Related Pages <#Related_Pages>`__

         .. rubric:: Roll Visibility Options
            :name: roll-visibility-options

         .. rubric:: Output Visibility
            :name: output-visibility

         These roll options control who is able to see the result of a
         given roll.

         -  **[s: ]**, **[self: ]** makes the roll visible only to the
            player who made the roll.
         -  **[g: ]**, **[gm: ]** makes the roll visible only to GMs.
         -  **[w("name"): ]**, **[whisper("name"): ]** makes the roll
            visible to the selected player.

         These roll options can be combined to make a roll visible to
         multiple people. If none of these options are used, output is
         visible to everyone.

         **[w(): ]** can also take more than one player name as an
         argument:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [w("Fred", "Joe"): d20]

         It can also take a JSON list containing player names:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: names = json.fromList("Fred, Joe")]

               #. .. code-block:: none

                     [w(names): d20]

         If a chat message would appear empty because everything in it
         is hidden from the player, the message is not displayed.

         .. rubric:: Tooltip Visibility
            :name: tooltip-visibility

         These options control who can see the tooltip showing detailed
         roll output. If the roll doesn't have a tooltip, these have no
         effect.

         -  **[st: ]**, **[selftt: ]** makes the tooltip visible only to
            the player who made the roll.
         -  **[gt: ]**, **[gmtt: ]** makes the tooltip visible only to
            GMs.

         These options can be combined with each other and with the
         other output options. If neither of these options are used, the
         tooltip is visible to everyone.

         .. rubric:: Related Pages
            :name: related-pages

         -  `Roll Types and Options <Macros:Roll:types>`__
         -  `Branching and Looping Roll
            Options <Macros:Branching_and_Looping>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Macros:Roll:output&oldid=3948"

