========================
clearLights - MapToolDoc
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

   .. rubric:: clearLights
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

            -  `1 clearLights()
               Function <#clearLights.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: clearLights() Function
            :name: clearlights-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Turns off all of the `light
            sources </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            for the `Current Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     clearLights()

               #. .. code-block:: none

                     clearLights(id)

               #. .. code-block:: none

                     clearLights(id, mapname)

         **Parameters**

         -  ``id`` - The token ``id`` of the token for which to turn off
            all light sources, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To turn off all of the light sources for the current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: clearLights()]

            To turn off all the lights sources on the map you could run
            the following script, note you will have to be the GM or run
            it as part of a trusted macro.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Ok Kids lights out!

                  #. .. code-block:: none

                        [h,foreach(tok, getTokens()), code: { [token(tok): clearLights()]}]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=clearLights&oldid=7549"

