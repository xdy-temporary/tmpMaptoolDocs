=========================
findDrawings - MapToolDoc
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

   .. rubric:: findDrawings
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

            -  `1 findDrawings()
               Function <#findDrawings.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: findDrawings() Function
            :name: finddrawings-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns the id or ids of any drawing on the specified map
            that match the name parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     findDrawings(mapName, name)

               #. .. code-block:: none

                     findDrawings(mapName, name, delim)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``name`` - A string containing name of the searched for
            drawings. The only way to name a drawing is via the Draw
            Explorer interface.
         -  ``delim`` - Optional separator. If not specified the default
            value ``","`` is used. If ``"json"`` is specified, a JSON
            array is returned instead of a String List.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:id=findDrawings("Grasslands", "block")]

                  #. .. code-block:: none

                        [h:setFillColor("Grasslands", id,"#000000")]

                  #. .. code-block:: none

                        [h:refreshDrawing("Grasslands", id)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setFillColor() </rptools/wiki/setFillColor>`__
            `refreshDrawing() </rptools/wiki/refreshDrawing>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=findDrawings&oldid=7040"

