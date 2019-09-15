=============================
movedOverDrawing - MapToolDoc
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

   .. rubric:: movedOverDrawing
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

            -  `1 movedOverDrawing()
               Function <#movedOverDrawing.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: movedOverDrawing() Function
            :name: movedoverdrawing-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Use to check if a given path has crossed through a specified
            drawing. Returns a JSON array with coordinates of all cells
            in the path that overlap with the area defined by the given
            drawing.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDrawingInfo(mapName, drawingId, path)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.
         -  ``path`` - JSON array of X/Y coordinate such as that
            returned by `getLastPath() <getLastPath>`__

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: lp = getLastPath()]

                  #. .. code-block:: none

                        [h: id = findDrawings(getCurrentMapName(),"fig1")] 

                  #. .. code-block:: none

                        [r: movedOverDrawing(getCurrentMapName(),id,lp)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDrawingInfo() <getDrawingInfo>`__
            `getLastPath() <getLastPath>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=movedOverDrawing&oldid=7383"

