=================================
Target a Visible NPC - MapToolDoc
=================================

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

   .. rubric:: Target a Visible NPC
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

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         This macro allows a player to pick-up a NPC among those he can
         currently see. Note that this is about the player's view and
         not the currently selected token's view. You may then store the
         target's name in the token's properties to ease further
         actions.

         Basically, the macro gets the list of all NPCs available (with
         `getNPCNames() <getNPCNames>`__) and the list of
         all visible tokens (with
         `getVisibleTokenNames() <getVisibleTokenNames>`__).
         Then, the intersection will provide visible NPCs.

         .. rubric:: Macro
            :name: macro

         **1.3b53+**

         --------------

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     /self 

               #. .. code-block:: none

                     [h: lsVisibleNpc = json.intersection( getNPCNames("json"), getVisibleTokenNames("json") )]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     // Abort if no target found (intersection returned an empty list)

               #. .. code:: de2

                     [h: assert(json.length(lsVisibleNpc), "No visible NPC", 0)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     // UI: popup a list for selection

               #. .. code-block:: none

                     [h: input("index|"+json.toList(lsVisibleNpc)+"|My target is|LIST") ]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     // Retrieve the first element, so we only get the name (and not ["name"])

               #. .. code-block:: none

                     [h: currentTgt = json.get(lsVisibleNpc, index) ]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     // Display message to be sure of what has just been done

               #. .. code-block:: none

                     Current target : {currentTgt}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Target_a_Visible_NPC&oldid=4147"

