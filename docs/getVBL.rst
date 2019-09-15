===================
getVBL - MapToolDoc
===================

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

   .. rubric:: getVBL
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

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getVBL() Function
            :name: getvbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b90**

         .. container:: template_description

            Gets the Vision Blocking Layer (VBL) shapes for the area
            specified in the ``shape`` parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVBL(shape,format)

         This function retrieves the VBL found in the given shape.

         **Parameters**

         -  ``shape`` - A JSON object as described in
            `drawVBL() </rptools/wiki/drawVBL>`__.
         -  ``format`` - Boolean. Returns a JSON object if
            ``false``\ (``0``), or an JSON array of coordinates if
            ``true``\ (``1``). In either case, the returned shape covers
            the VBL found in the area.

         | 

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:rectangle = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]
                  [r:vblData   = getVBL(rectangle , 0)]

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking </rptools/wiki/Introduction_to_Vision_Blocking>`__,
            `eraseVBL() </rptools/wiki/eraseVBL>`__,
            `drawVBL() </rptools/wiki/drawVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getVBL&oldid=7437"

