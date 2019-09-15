=========================================
isExternalMacroAccessAllowed - MapToolDoc
=========================================

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

   .. rubric:: isExternalMacroAccessAllowed
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

         .. rubric:: isExternalMacroAccessAllowed() Function
            :name: isexternalmacroaccessallowed-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns ``true``\ (``1``) if the client is configured to
            allow external macro access (see **Allow External Macro
            Access** in MapTool Preferences). When enabled, this allows
            the use of other macro functions such as
            `exportData() <exportData>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isExternalMacroAccessAllowed()

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **1. Test to see if the current client can access external
            resources from macros.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        This client has external access [r,if(isExternalMacroAccessAllowed()): "Enabled"; "Disabled"]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isExternalMacroAccessAllowed&oldid=7080"

