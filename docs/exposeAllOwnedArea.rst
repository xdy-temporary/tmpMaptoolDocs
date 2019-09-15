===============================
exposeAllOwnedArea - MapToolDoc
===============================

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

   .. rubric:: exposeAllOwnedArea
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

         .. rubric:: exposeAllOwnedArea() Function
            :name: exposeallownedarea-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Exposes all area visible to tokens owned by the current
            player that have vision turned on in the token editor. The
            actual area exposed depends on server settings (like
            **Individual Views**) and various MapTool Preferences.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     exposeAllOwnedArea(mapName)

         **Parameters**

         -  ``mapName`` - The name of an existing map within the
            campaign. This map does not need to be the one currently
            visible. If the map holds no tokens with vision owned by the
            current player, no additional fog-of-war is exposed, but fog
            already exposed is not reset.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `exposeFOW() </rptools/wiki/exposeFOW>`__,
            `toggleFoW() </rptools/wiki/toggleFoW>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=exposeAllOwnedArea&oldid=7546"

