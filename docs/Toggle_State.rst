=========================
Toggle State - MapToolDoc
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

   .. rubric:: Toggle State
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

         .. rubric:: Toggle State
            :name: toggle-state

         This is a very simple macro that allows you to toggle the state
         of selected tokens. It is potentially useful to a GM who has
         players that can mark - simply set the name of the state at the
         beginning of the macro. It is useful to have a different button
         (stored locally or in campaign macros) for each player's mark.
         You can quickly select several enemies when marking with a
         blast/burst power or for switching marks you can select both
         the old mark and the new mark and it will toggle as wanted.

         Special thanks to zEal who made this macro for me.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: StateName = "Marked_red" ]

               #. .. code-block:: none

                     [h, foreach( Selected, getSelected("json") ):

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     setState(StateName,if(getState(StateName, Selected),0,1),Selected)

               #. .. code:: de2

                      

               #. .. code-block:: none

                     ]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Toggle_State&oldid=3743"

