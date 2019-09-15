===========================
hasLightSource - MapToolDoc
===========================

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

   .. rubric:: hasLightSource
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

            -  `1 hasLightSource()
               Function <#hasLightSource.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: hasLightSource() Function
            :name: haslightsource-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns 1 if the `Current
            Token </rptools/wiki/Current_Token>`__ has any `light
            sources </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            that match the criteria passed in or 0 if there are no
            matches. If no arguments are passed to the function then it
            will return 1 if any `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            is on. If only the first argument is passed it will return 1
            if any `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            of that `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__
            is on. If both arguments are passed to the function it will
            return 1 if the `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            with the specified name and specified `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__
            is on.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hasLightSource()

               #. .. code-block:: none

                     hasLightSource(type)

               #. .. code-block:: none

                     hasLightSource(type, name)

               #. .. code-block:: none

                     hasLightSource(type, name, id)

               #. .. code:: de2

                     hasLightSource(type, name, id, mapname)

         **Parameters**

         -  ``type`` - The `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__,
            (e.g. "Generic", "D20"). If "*" is entered, all light
            sources types are checked. Defaults to "*".
         -  ``name`` - the name of the `light
            source </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__.
            If "*" is entered, all light sources names are checked.
            Defaults to "*".
         -  ``id`` - The token ``id`` of the token which is checked for
            light sources, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Check to see if any light source is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource()]

            Check to see if a "D20" lamp is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource("D20", "Lamp - 15")]

            Check to see if any "D20" light source is on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: l = hasLightSource("D20")

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options. Changed behavior if ``type`` or ``name`` are set
               to "*".

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=hasLightSource&oldid=7548"

