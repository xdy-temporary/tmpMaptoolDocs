====================
drawVBL - MapToolDoc
====================

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

   .. rubric:: drawVBL
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

            -  `1 drawVBL() Function <#drawVBL.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: drawVBL() Function
            :name: drawvbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b89**

         .. container:: template_description

            Draws Vision Blocking Layer (VBL) shapes.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     drawVBL(shapesList)

         This function works EXACTLY the same as
         `eraseVBL() <eraseVBL>`__ with the ONLY
         difference that drawVBL draws the shapes on the vision blocking
         layer and `eraseVBL() <eraseVBL>`__ erases them.

         | 
         | **Parameters**

         -  ``shapesList`` - A `JSON Array <JSON_Array>`__
            of `JSON objects <JSON_Object>`__, one of the
            latter for each VBL shape.

         The shapes can be one of ``"Rectangle"``, ``"Circle"``,
         ``"Polygon"`` or ``"Cross"``.

         | 
         | **Shape - Rectangle and Cross**
         | *Required arguments.*

         -  ``"x"`` - Abscissa in pixels. (aka: X-Coordinate)
         -  ``"y"`` - Ordinate in pixels. (aka: Y-Coordinate)
         -  ``"w"`` - Width in pixels. Cannot be smaller than ``4``.
         -  ``"h"`` - Height in pixels. Cannot be smaller than ``4``.

         *Optional arguments*

         -  ``"r"`` - Rotation on centre axis in degrees. Using default
            mathematical system: ``0`` is no rotation, ``+`` is
            clockwise, ``-`` is counterclockwise.
         -  ``"facing"`` - Rotation on centre axis in degrees. Using the
            MT facing system: ``0`` will rotate the shape 90 degrees
            anticlockwise, ``+`` is counterclockwise, ``-`` is
            clockwise. When using both ``"r"`` and ``"facing"``, then
            ``"facing"`` takes precedence.
         -  ``"rx"`` - Rotation centre offset in pixels.
         -  ``"ry"`` - Rotation centre offset in pixels. When used the
            centre over which the shape is rotated is positioned at the
            (rx,ry) coordinate. The centre defaults to the actual centre
            of the shape.
         -  ``"fill"`` - If ``1`` fills rectangle, otherwise creates
            empty shape.
         -  ``"thickness"`` - Line thickness from ``2`` to ``n`` pixels.
            Lower than ``2`` or empty defaults to ``2``. Even numbers
            only (odd numbers get rounded down by one). Can't be bigger
            than width or height.
         -  ``"scale"`` - If provided number not ``0``, will scale
            rectangle by ``x``, ie scale: ``2`` is double, scale:
            ``0.5`` is half.

         | **Note** These two shapes (cross and rectangle) are created
           such that the shape INCLUDING the thickness of the line is
           always conform to the ``"x"``, ``"y"``, ``"w"`` and ``"h"``
           parameters. E.g. a 100x100px rectangle with ``thickness`` 20
           will result in a 100x100px rectangle. These are the ONLY
           shapes for which this check is made! Without the check the
           rectangle would cover an area of 110x110px (10 on the inside
           and 10 on the outside of the shape). This correction is also
           the reason why shapes cannot be smaller than 4px and the
           ``thickness`` is always even.

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:rectangle = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]
                  [h:cross = "{'shape':'cross','x':-50,'y':-50,'w':50,'h':100,'r':30,'fill':1,'thickness':1,'scale':2}"]

         | 
         | **Shape - Circle**
         | *Required arguments*

         -  ``"x"`` - see ``"shape":"rectangle"``.
         -  ``"y"`` - see ``"shape":"rectangle"``.
         -  ``"radius"`` - This is the distance in pixels between the
            centre of the circle to its furthest point (is one of its
            vertices).
         -  ``"sides"`` - Specifies how many sides the polygon will have
            to approximate a circle, from ``3`` to ``100``.

         *Optional arguments*

         -  ``"r"`` - see ``"shape":"rectangle"``.
         -  ``"facing"`` - see ``"shape":"rectangle"``.
         -  ``"rx"`` - see ``"shape":"rectangle"``.
         -  ``"ry"`` - see ``"shape":"rectangle"``.
         -  ``"fill"`` - see ``"shape":"rectangle"``.
         -  ``"thickness"`` - see ``"shape":"rectangle"``.
         -  ``"scale"`` - see ``"shape":"rectangle"``.

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:circle = "{'shape':'circle', 'X':50, 'Y':100, 'radius':200, 'thickness':3, 'fill':0, 'sides':12,'r':45}"]

         Note that this shape can be used to easily create regular
         polygons, e.g. a triangle:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  {"shape":"circle", "X":50, "Y":100, "radius":200, "sides":3, "thickness":3, "fill":0, "r":30}

         and a square (note that this square does *not* have the
         dimensions 200x200 but ~105x105 !):

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  {"shape":"circle", "X":50, "Y":100, "radius":200, "thickness":3, "fill":0, "sides":4,"r":45}

         | … or hexagons.

         | **Shape - Polygon**
         | *Required arguments*

         -  ``"points"`` - `JSON Array <JSON_Array>`__ of
            2 or more ``"x"``, ``"y"`` coordinates.

         *Optional arguments*

         -  ``"close"`` - If ``1`` then it will close the polygon
            otherwise it will leave it open.
         -  ``"r"`` - see ``"shape":"rectangle"``.
         -  ``"facing"`` - see ``"shape":"rectangle"``.
         -  ``"rx"`` - see ``"shape":"rectangle"``.
         -  ``"ry"`` - see ``"shape":"rectangle"``.
         -  ``"fill"`` - see ``"shape":"rectangle"``.
         -  ``"thickness"`` - see ``"shape":"rectangle"``.

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:polygon = "{'shape':'polygon','r':0,'close':1,'thickness':10,'points':[{'x':0,'y':0},{'x':200,'y':200},{'x':150,'y':10}]}"]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            This example builds an array of the object from the above
            examples and then feeds that array into the drawVBL function

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:rectangle    = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]

                  #. .. code-block:: none

                        [h:cross    = "{'shape':'cross','x':-50,'y':-50,'w':50,'h':100,'r':30,'fill':1,'thickness':1,'scale':2}"]

                  #. .. code-block:: none

                        [h:circle  = "{'shape':'circle', 'X':50, 'Y':100, 'radius':200, 'thickness':3, 'fill':0, 'sides':12,'r':45}"]

                  #. .. code-block:: none

                        [h:polygon    = "{'shape':'polygon','r':0,'close':1,'thickness':10,'points':[{'x':0,'y':0},{'x':200,'y':200},{'x':150,'y':10}]}"] 

                  #. .. code:: de2

                        [h:objectArrary  = json.append('',rectangle, cross, circle, polygon)]

                  #. .. code-block:: none

                        [h:drawVBL(objectArrary)]

            | results in:

            |VBL Shapes.jpg|

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking <Introduction_to_Vision_Blocking>`__
            , `eraseVBL() <eraseVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=drawVBL&oldid=7196"

