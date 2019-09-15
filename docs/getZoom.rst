====================
getZoom - MapToolDoc
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

   .. rubric:: getZoom
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

            -  `1 getZoom() Function <#getZoom.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getZoom() Function
            :name: getzoom-function

         .. container:: template_version

            • **Introduced in version 1.4**

         .. container:: template_description

            Returns the current zoom level of the viewport in
            percentage, where 1 (=100%) is the default. This is the same
            number as what you find at the bottom of the Maptool window.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getZoom()

         **Parameters** None.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Zoom in by a factor 2

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: z = getZoom()]

                  #. .. code-block:: none

                        [h: setZoom(2*z)]

            Zoom in by one 10%

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: z = getZoom()]

                  #. .. code-block:: none

                        [h: setZoom(z+0.1)]

            Zoom out by 10%

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: z = getZoom()]

                  #. .. code-block:: none

                        [h: setZoom(z-0.1)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setZoom() </rptools/wiki/setZoom>`__,
            `getTokenX() </rptools/wiki/getTokenX>`__,
            `getTokenY() </rptools/wiki/getTokenY>`__,

            `goto() </rptools/wiki/goto>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getZoom&oldid=6348"

