==================================
addAllPCsToInitiative - MapToolDoc
==================================

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

   .. rubric:: addAllPCsToInitiative
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

         .. rubric:: addAllPCsToInitiative() Function
            :name: addallpcstoinitiative-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_description

            Adds all the `PC
            tokens </maptool/index.php?title=Token:PC_token&action=edit&redlink=1>`__
            on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            to the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function returns the number of
            `tokens </rptools/wiki/Token:token>`__ that were added to
            the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function will not assign any initiative value to the
            `tokens </rptools/wiki/Token:token>`__, you can use the
            ```setInitiative()`` </rptools/wiki/setInitiative>`__

            function to set the initiative value of tokens.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: noTokens = addAllPCsToInitiative()]

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Added [r: addAllNPCsToInitiative()] NPCs to the initiative panel.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setInitiative() </rptools/wiki/setInitiative>`__
            `addAllNPCsToInitiative() </rptools/wiki/addAllNPCsToInitiative>`__
            `addAllToInitiative() </rptools/wiki/addAllToInitiative>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addAllPCsToInitiative&oldid=2227"

