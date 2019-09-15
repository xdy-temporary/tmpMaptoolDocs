========================
getDistance - MapToolDoc
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

   .. rubric:: getDistance
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

            -  `1 getDistance()
               Function <#getDistance.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getDistance() Function
            :name: getdistance-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Returns the distance between two tokens or objects.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistance(target)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistance(target, units)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistance(target, units, source)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDistance(target, units, source, metric)

         **Parameters**

         -  ``target`` - The id of the token that the distance is
            measured to.
         -  ``units`` - If set to ``false``\ (``0``), the distance is
            given in cells, otherwise the default is to return the
            distance in Distance Per Cell units.
         -  ``source`` - The id of the token to measure the distance
            from, the default is the current token.
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

            To get the distance from the current token to the *Altar*.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistance("Altar")]

            To get the distance between the *Altar* and the *Sacrifice*
            in the number of squares or hexes.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistance("Altar", 0, "Sacrifice")]

            To get the distance between the *Altar* and the *Sacrifice*
            in *map distance* units.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistance("Altar", 1, "Sacrifice")]

            To get the straight line distance between the *Altar* and
            the *Sacrifice*.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: dist = getDistance("Altar", 1, "Sacrifice", "NO_GRID")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDistanceToXY() </rptools/wiki/getDistanceToXY>`__
            `getTokens() </rptools/wiki/getTokens>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b55** - Added the optional ``metric`` argument.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getDistance&oldid=6352"

