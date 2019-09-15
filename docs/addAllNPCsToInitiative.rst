===================================
addAllNPCsToInitiative - MapToolDoc
===================================

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

   .. rubric:: addAllNPCsToInitiative
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

            -  `1 Function addAllNPCsToInitiative()
               Function <#Function_addAllNPCsToInitiative.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: Function addAllNPCsToInitiative() Function
            :name: function-addallnpcstoinitiative-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_description

            Adds all the `NPC
            tokens </maptool/index.php?title=Token:NPC_token&action=edit&redlink=1>`__
            on the current
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
            function

            to set the initiative value of tokens.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     addAllNPCsToInitiative()

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: noTokens = addAllNPCsToInitiative()]

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Added [r: addAllNPCsToInitiative()] NPCs to the initiative panel.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setInitiative() <setInitiative>`__
            `addAllPCsToInitiative() <addAllPCsToInitiative>`__
            `addAllToInitiative() <addAllToInitiative>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addAllNPCsToInitiative&oldid=2226"

