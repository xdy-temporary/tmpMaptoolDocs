========================
getViewArea - MapToolDoc
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

   .. rubric:: getViewArea
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

            -  `1 getViewArea()
               Function <#getViewArea.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getViewArea() Function
            :name: getviewarea-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns the limits of the visible area of the map window,
            given in either pixels or cell coordinates depending on the
            first parameter. The result is in a ";" delimited String as
            default or can be configured by setting the delimiter or
            using Json.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getViewArea()

               #. .. code-block:: none

                     getViewArea(pixels)

               #. .. code-block:: none

                     getViewArea(pixels, delim)

         **Parameters**

         -  ``pixels`` - if set to true (1) means the returned
            coordinates are measured in pixels. If set to false (0) the
            returned coordinates are measured in map cells. Defaults to
            ``true``.
         -  ``delim`` - if set to "json" means the returned coordinates
            are defined in JSON style. Otherwise a String property list
            is returning using ``delim`` as a delimiter. Defaults to
            ``;``.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Get the viewport dimensions of the current client:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getViewArea()] <!-- Default pixels -->

                  #. .. code-block:: none

                        [r: getViewArea(0)] <!-- in Grid Cells -->

                  #. .. code-block:: none

                        [r: getViewArea(1)] <!-- in Pixels -->

                  #. .. code-block:: none

                        [r: getViewArea(0, "json")] <!-- Cells as JSON -->

                  #. .. code:: de2

                        [r: getViewArea(1, "json")] <!-- Pixels as JSON -->

                  #. .. code-block:: none

                        [r: getViewArea(0, ",")] <!-- Cells as "," separated String properties: -->

                  #. .. code-block:: none

                        [r: getViewArea(1, ";")] <!-- Pixels as ";" separated String properties: -->

            Output:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=17; endY=12 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616 

                  #. .. code-block:: none

                        {"startX":0,"startY":0,"endX":886,"endY":616} 

                  #. .. code:: de2

                        {"startX":0,"startY":0,"endX":886,"endY":616} 

                  #. .. code-block:: none

                        startX=0, startY=0, endX=886, endY=616 

                  #. .. code-block:: none

                        startX=0; startY=0; endX=886; endY=616

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setViewArea() <setViewArea>`__,
            `goto() <goto>`__,
            `setZoom() <setZoom>`__,
            `getZoom() <getZoom>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getViewArea&oldid=7442"

