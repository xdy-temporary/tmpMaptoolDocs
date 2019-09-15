=====================
setLight - MapToolDoc
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

   .. rubric:: setLight
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

            -  `1 setLight() Function <#setLight.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setLight() Function
            :name: setlight-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the `light
            sources </maptool/index.php?title=Map:light_source&action=edit&redlink=1>`__
            of the `Current
            Token </maptool/index.php?title=Token:Current_Token&action=edit&redlink=1>`__.
            If the value is ``false``\ (``0``) then the `light
            source </maptool/index.php?title=Map:light_source&action=edit&redlink=1>`__
            is turned off; otherwise, it is turned on.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setLight(type, name, value)

               #. .. code-block:: none

                     setLight(type, name, value, id)

               #. .. code-block:: none

                     setLight(type, name, value, id, mapname)

         **Parameters**

         -  ``type`` - The `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__,
            (e.g. "Generic", "D20").
         -  ``name`` - The name of the `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__.
         -  ``value`` - If ``true``\ (``1``) sets the light on, if
            ``false``\ (``0``) turns it off.
         -  ``id`` - The token ``id`` of the token to change the light
            sources, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setLight("D20", "Candle - 5", 1)]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setLight&oldid=7550"

