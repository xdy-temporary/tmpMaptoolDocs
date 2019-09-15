=============================
setDrawingEraser - MapToolDoc
=============================

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

   .. rubric:: setDrawingEraser
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

            -  `1 setDrawingEraser()
               Function <#setDrawingEraser.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setDrawingEraser() Function
            :name: setdrawingeraser-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Sets the eraser setting of the drawing that corresponds to
            the map and drawing id. If Set to ``false``\ (``0``) the
            drawing will be displayed normally, but if set to
            ``true``\ (``1``) the drawing will erase all below.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setDrawingEraser(mapName, drawingId, boolean)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.
         -  ``boolean`` - The value of the setting to set,
            ``true``\ (``1``) or ``false``\ (``0``).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setDrawingEraser("Grasslands", "0000000094218C675800000000000000",0)]

                  #. .. code-block:: none

                        [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]

                  #. .. code-block:: none

                        [h:setDrawingEraser("Grasslands", "00000000CCF6B567CC00000000000000",1)]

                  #. .. code-block:: none

                        [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDrawingEraser() <getDrawingEraser>`__
            `refreshDrawing() <refreshDrawing>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setDrawingEraser&oldid=7050"

