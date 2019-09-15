============================
getDistanceToXY - MapToolDoc
============================

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

   .. rubric:: getDistanceToXY
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

            -  `1 getDistanceToXY()
               Function <#getDistanceToXY.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getDistanceToXY() Function
            :name: getdistancetoxy-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the distance to a target grid cell.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistanceToXY(x, y)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistanceToXY(x, y, units)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistanceToXY(x, y, units, source)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistanceToXY(x, y, units, source, metric)

         **Parameters**

         -  ``x`` - The X coordinate of the target grid cell.
         -  ``y`` - The Y coordinate of the target grid cell.
         -  ``units`` - If set to ``false``\ (``0``) the distance is
            returned in cells. Default is returning Distance Per Cell
            units.
         -  ``source`` - The id of the token to measure the distance
            from. Default is the current token.
         -  
         -  ``metric`` - The movement metric to use which defaults to
            the movement metric in the users preferences, the metric can
            be one of the following strings

            -  ``NO_GRID`` - The grid is ignored and straight line
               distance between the tokens is returned.
            -  ``ONE_TWO_ONE`` - First Diagonal movement costs 1, second
               2, and so on (Square grid only).
            -  ``ONE_ONE_ONE`` - Diagonal movement costs a single square
               (Square grid only).
            -  ``MANHATTAN`` - Diagonal movement costs 2 (Square grid
               only).
            -  ``NO_DIAGONALS`` - No diagonal movement is allowed
               (Square grid only).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To get the distance from the current token to 10,10.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistanceToXY(10, 10)]

            To get the distance between the *Altar* and 10, 10 in the
            number of squares or hexes.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistanceToXY(10, 10, 0, "Altar")]

            To get the distance between the *Altar* and 10, 10 in *map
            distance* units.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistanceToXY(10, 10, 1, "Altar")]

            To get the straight line distance between the *Altar* and
            10, 10.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistanceToXY(10, 10, 1, "Altar", "NO_GRID")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDistance() <getDistance>`__
            `getTokens() <getTokens>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b55** - Added the optional ``metric`` argument.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getDistanceToXY&oldid=3054"

