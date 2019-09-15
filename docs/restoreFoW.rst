=======================
restoreFoW - MapToolDoc
=======================

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

   .. rubric:: restoreFoW
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

            -  `1 restoreFoW() Function <#restoreFoW.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: restoreFoW() Function
            :name: restorefow-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.3**

         .. container:: template_description

            Resets all fog of war (FoW) for the map.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     restoreFoW()

               #. .. code-block:: none

                     restoreFoW(mapname)

         This function resets all FoW for the current map or the
         indicated map if the optional map name is supplied. Duplicates
         the FoW reset available through **Map Menu** -> **Restore
         Fog-of-War** or when you import a new map sans dialog.

         **Parameters**

         -  ``mapname`` - Optional map name.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     <!-- Restore all Fog of War on current map -->
                     [h: restoreFoW()]
                     <!-- Restore all Fog of War on named map -->
                     [h: restoreFoW("Skull Mountain")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction_to_Lights_and_Sights#Fog_of_War </rptools/wiki/Introduction_to_Lights_and_Sights#Fog_of_War>`__,
            `toggleFoW() </rptools/wiki/toggleFoW>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=restoreFoW&oldid=7450"

