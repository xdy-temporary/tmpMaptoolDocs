=====================
hasMacro - MapToolDoc
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

   .. rubric:: hasMacro
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

         .. rubric:: hasMacro() Function
            :name: hasmacro-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if a `macro
            button </rptools/wiki/Macro_Button>`__ with the specified
            label exists on the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hasMacro(label)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hasMacro(label, id)

         **Parameters**

         -  ``label`` - The label of the macro to check for.
         -  ``id`` - The token ``id`` of the token that the function is
            executed on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added optional token ``id`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=hasMacro&oldid=5587"

