============================
movedOverPoints - MapToolDoc
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

   .. rubric:: movedOverPoints
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *lastPath-format specified,
              define/explain return value, examples*

         .. rubric:: movedOverPoints() Function
            :name: movedoverpoints-function

         .. container:: template_version

            • **Introduced in version 1.3.b75**

         .. container:: template_description

            Use to check if a token has moved through a shape that is
            defined by an array of pixel coordinates (formatted like the
            one received from
            `getLastPath() </rptools/wiki/getLastPath>`__ or the
            ``onTokenMove`` event.
            Returns a JSON array with coordinates of all cells in the
            token's path that overlap with the area defined by the given
            points.

            Where each coordinate pair returned is dependent on the grid
            type:

            -  Square: Coordinates are the top-left corner.
            -  Hex: Coordinates are the center point of the cell.
            -  Isometric: Coordinates are the right-most point of the
               cell.
            -  Gridless: Returns just the top-left corner of the token's
               ending location.

            .. rubric:: Usage
               :name: usage

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        movedOverPoints(points)

                  #. .. code-block:: none

                        movedOverPoints(points,path)

            **Parameters**

            -  ``points`` - JSON array of X/Y coordinate X/Y pairs that
               defines a polygon
            -  ``path`` - JSON array of X/Y coordinate such as that
               returned by `getLastPath() </rptools/wiki/getLastPath>`__

            .. rubric:: Example
               :name: example

            .. container:: template_example

               .. container:: mw-geshi mw-code mw-content-ltr

                  .. container:: mtmacro source-mtmacro

                     #. .. code-block:: none

                           <!-- lets define a shape -->

                     #. .. code-block:: none

                            

                     #. .. code-block:: none

                           [h: jsonArray = json.append("",

                     #. .. code-block:: none

                               json.set("", "x",   0, "y",   0),

                     #. .. code:: de2

                               json.set("", "x",   0, "y", 100),

                     #. .. code-block:: none

                               json.set("", "x", 100, "y", 100),

                     #. .. code-block:: none

                               json.set("", "x",   100, "y", 0)

                     #. .. code-block:: none

                           )]

                     #. .. code-block:: none

                            

                     #. .. code:: de2

                           <!-- check if token in context has moved through that shape -->

                     #. .. code-block:: none

                           [r: movedOverPoints(jsonArray)]

               **With Second Parameter**

               .. container:: mw-geshi mw-code mw-content-ltr

                  .. container:: mtmacro source-mtmacro

                     #. .. code-block:: none

                           [h: jsonArray = json.append("",

                     #. .. code-block:: none

                               json.set("", "x", 250, "y", 250),

                     #. .. code-block:: none

                               json.set("", "x", 250, "y", 550),

                     #. .. code-block:: none

                               json.set("", "x", 550, "y", 550),

                     #. .. code:: de2

                               json.set("", "x", 550, "y", 250)

                     #. .. code-block:: none

                           )]

                     #. .. code-block:: none

                            

                     #. .. code-block:: none

                           Last Path: [r: lastPath = getLastPath()]

                     #. .. code-block:: none

                           <br>

                     #. .. code:: de2

                           Moved Over: [r: movedOverPoints(jsonArray,lastPath)]

         .. container:: printfooter

            Retrieved from
            "http://lmwcs.com/maptool/index.php?title=movedOverPoints&oldid=7354"

