========================
setViewArea - MapToolDoc
========================

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

   .. rubric:: setViewArea
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

            -  `1 setViewArea()
               Function <#setViewArea.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setViewArea() Function
            :name: setviewarea-function

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Sets the currently viewed screen area, set by two sets of
            cell coordinates, so that the two cells are at the edge of
            the screen. If the map is "gridless", the coordinates will
            be pixel coordinates. A final optional parameter causes the
            view of any connected players to be set the same. Only GMs
            or trusted macros can trigger the view of all players to
            change.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setViewArea(startX, startY, endX, endY [, pixels [, allPlayers]])

         **Parameters**

         -  ``startX`` - the x coordinate of the cell that will mark the
            upper left corner of the displayed area.
         -  ``startY`` - the y coordinate of the cell that will mark the
            upper left corner of the displayed area.
         -  ``endX`` - the x coordinate of the cell that will mark the
            lower right corner of the displayed area.
         -  ``endY`` - the x coordinate of the cell that will mark the
            lower right corner of the displayed area
         -  ``pixels`` - an optional parameter that if set to true (1)
            means the coordinates are measured in pixels. If set to
            false (0) the coordinates are measured in map cells.
            Defaults to true (1).
         -  ``allPlayers`` - Optional: If set to true (1) and called
            from a trusted macro, all players views will be set.
            Defaults to 0

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Set the viewport of the current client such that it at least
            sees the corners of the area with the following CELL
            coordinates:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setViewArea(0,0,30,20, 0)]

            When the GM runs the macro change the viewport in PIXEL
            coordinates on ALL clients, else only on the current client:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setViewArea(0, 0, 300, 200, 1, isGM())]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getViewArea() </rptools/wiki/getViewArea>`__,
            `getTokenY() </rptools/wiki/getTokenY>`__,
            `goto() </rptools/wiki/goto>`__,
            `setZoom() </rptools/wiki/setZoom>`__,
            `getZoom() </rptools/wiki/getZoom>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setViewArea&oldid=7280"

