=====================
setLayer - MapToolDoc
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

   .. rubric:: setLayer
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

            -  `1 setLayer() Function <#setLayer.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setLayer() Function
            :name: setlayer-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__
            that a `Token </rptools/wiki/Token>`__ is on.
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

                     setLayer(layer)

               #. .. code-block:: none

                     setLayer(layer, id)

               #. .. code-block:: none

                     setLayer(layer, id, forceshape)

               #. .. code-block:: none

                     setLayer(layer, id, forceshape, mapname)

         **Parameters**

         -  ``layer`` - The layer to move the
            `Token </rptools/wiki/Token>`__ to.
         -  ``id`` - The token ``id`` of the token which has its layer
            set, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.
         -  ``forceshape`` - If ``true``\ (``1``), change the token
            shape type to TOP_DOWN if the layer is ``OBJECT``, and to a
            shape reflecting its image if the layer is ``TOKEN``.
            Defaults to ``true``\ (``1``).
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            When an NPC token is dead, send it to the Object layer,
            otherwise leave it where it is.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: layerName = getLayer()]

                  #. .. code-block:: none

                        [h: layerName = if(state.Dead&&isNPC(), "OBJECT", layerName)]

                  #. .. code-block:: none

                        [h: setLayer(layerName)]

            Toggle a token between the Hidden and Token layers.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: layerName = getLayer()]

                  #. .. code-block:: none

                        [h: layerName = if(layerName=="GM", "TOKEN", "GM")]

                  #. .. code-block:: none

                        [h: setLayer(layerName)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getLayer() </rptools/wiki/getLayer>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setLayer&oldid=7541"

