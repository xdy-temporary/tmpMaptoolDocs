=====================
eraseVBL - MapToolDoc
=====================

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

   .. rubric:: eraseVBL
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

            -  `1 eraseVBL() Function <#eraseVBL.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: eraseVBL() Function
            :name: erasevbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b89**

         .. container:: template_description

            Erases Vision Blocking Layer (VBL) shapes.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     eraseVBL(shapesList)

         This function works EXACTLY the same as
         `drawVBL() <drawVBL>`__ with the ONLY difference
         that `drawVBL() <drawVBL>`__ draws the shapes on
         the vision blocking layer and eraseVBL erases them. For
         descriptions on parameters and more examples goto the
         `drawVBL() <drawVBL>`__ page.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            This example erases a (solid) block of VBL of 200x200
            pixels, centered on the origin of the map

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:rectangle    = "{'shape':'rectangle','x':0,'y':0,'w':200,'h':200, 'fill':1}"]

                  #. .. code-block:: none

                        [h:objectArrary = json.append('',rectangle)]

                  #. .. code-block:: none

                        [h:eraseVBL(objectArrary)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking <Introduction_to_Vision_Blocking>`__,
            `drawVBL() <drawVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=eraseVBL&oldid=7198"

