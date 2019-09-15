===============================
addAllToInitiative - MapToolDoc
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

   .. rubric:: addAllToInitiative
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

         .. rubric:: addAllToInitiative() Function
            :name: addalltoinitiative-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_description

            Adds all of the `tokens <Token:token>`__ on
            the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            to the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function returns the number of
            `tokens <Token:token>`__ that were added to
            the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function will not assign any initiative value to the
            `tokens <Token:token>`__, you can use the
            ```setInitiative()`` <setInitiative>`__

            function to set the initiative value of tokens.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: noTokens = addAllToInitiative()]

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Added [r: addAllNPCsToInitiative()] NPCs to the initiative panel.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setInitiative() <setInitiative>`__
            `addAllPCsToInitiative() <addAllPCsToInitiative>`__
            `addAllNPCsToInitiative() <addAllNPCsToInitiative>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addAllToInitiative&oldid=2228"

