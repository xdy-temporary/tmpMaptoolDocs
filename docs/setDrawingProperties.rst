=================================
setDrawingProperties - MapToolDoc
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

   .. rubric:: setDrawingProperties
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

            -  `1 setDrawingProperties()
               Function <#setDrawingProperties.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setDrawingProperties() Function
            :name: setdrawingproperties-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Sets the properties for a specified drawing. Currently this
            can only be used in conjunction with the
            getDrawingProperties function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setDrawingProperties(mapName, drawingId, properties)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.
         -  ``properties`` - The properties of another drawing.
            Currently this can only be delivered via the
            getDrawingProperties function

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:fromId="0000000074836E675D00000000000000"]

                  #. .. code-block:: none

                        [h:toId="0000000095C36B437D00000000000000"]

                  #. .. code-block:: none

                        [h:setDrawingProperties("Grasslands", toId, getDrawingProperties("Grasslands", fromId))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDrawingProperties() </rptools/wiki/getDrawingProperties>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setDrawingProperties&oldid=7052"

