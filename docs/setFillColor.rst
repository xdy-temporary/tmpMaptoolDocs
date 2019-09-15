=========================
setFillColor - MapToolDoc
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

   .. rubric:: setFillColor
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

            -  `1 setFillColor()
               Function <#setFillColor.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setFillColor() Function
            :name: setfillcolor-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Sets the colour or texture of the pen for a specified
            drawing.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setFillColor(mapName, drawingId, paint)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.
         -  ``paint`` - A string representing the fill colour or fill
            texture.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setFillColor("Grasslands", "0000000094218C675800000000000000","red")]

                  #. .. code-block:: none

                        [h:setFillColor("Grasslands", "0000000094218C675800000000000000","#ff0000")]

                  #. .. code-block:: none

                        [h:refreshDrawing("Grasslands", "0000000094218C675800000000000000")]

                  #. .. code-block:: none

                        [h:setFillColor("Grasslands", "00000000CCF6B567CC00000000000000","asset://ffff0fe019c241c7456b0ec0b347ef37")]

                  #. .. code:: de2

                        [h:refreshDrawing("Grasslands", "00000000CCF6B567CC00000000000000")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getFillColor() </rptools/wiki/getFillColor>`__
            `refreshDrawing() </rptools/wiki/refreshDrawing>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setFillColor&oldid=7053"

