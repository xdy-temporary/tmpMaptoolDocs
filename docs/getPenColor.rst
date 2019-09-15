========================
getPenColor - MapToolDoc
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

   .. rubric:: getPenColor
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

            -  `1 getPenColor()
               Function <#getPenColor.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getPenColor() Function
            :name: getpencolor-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns a string representing the colour or texture of the
            pen for a specified drawing. A colour will be returned in
            the hex format (i.e. "#000000" for black) while a texture
            will be returned as the asset url (i.e.
            "asset://ffff0fe019c241c7456b0ec0b347ef37")

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getPenColor(mapName, drawingId)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getPenColor("Grasslands", "0000000074836E675D00000000000000")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setPenColor() </rptools/wiki/setPenColor>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getPenColor&oldid=7047"

