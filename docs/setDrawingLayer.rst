============================
setDrawingLayer - MapToolDoc
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

   .. rubric:: setDrawingLayer
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

            -  `1 setDrawingLayer()
               Function <#setDrawingLayer.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setDrawingLayer() Function
            :name: setdrawinglayer-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.7**

         .. container:: template_description

            For a specified drawing, set the layer of the map to which
            the drawing belongs.
            The `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__
            is one of:

            -  ``TOKEN``
            -  ``GM`` also known as Hidden
            -  ``OBJECT``
            -  ``BACKGROUND``

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setDrawingLayer(mapName, drawingId, layer)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.
         -  ``layer`` - The layer to move the drawing to.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setDrawingLayer("Grasslands", "0000000074836E675D00000000000000","GM")]

                  #. .. code-block:: none

                        [h:refreshDrawing("Grasslands", "0000000074836E675D00000000000000")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDrawingLayer() </rptools/wiki/getDrawingLayer>`__
            `refreshDrawing() </rptools/wiki/refreshDrawing>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setDrawingLayer&oldid=7163"

