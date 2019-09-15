=====================
getNotes - MapToolDoc
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

   .. rubric:: getNotes
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

         .. rubric:: getNotes() Function
            :name: getnotes-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the `token
            notes </maptool/index.php?title=Notes&action=edit&redlink=1>`__
            for the `Current Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getNotes()

               #. .. code-block:: none

                     getNotes(id)

               #. .. code-block:: none

                     getNotes(id, mapname)

         | 
         | **Parameter**

         -  ``id`` - The token ``id`` of the token to get the notes
            from.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

         | 

         See also `setNotes </rptools/wiki/setNotes>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getNotes&oldid=7537"

