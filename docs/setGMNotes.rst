=======================
setGMNotes - MapToolDoc
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

   .. rubric:: setGMNotes
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

         .. rubric:: setGMNotes() Function
            :name: setgmnotes-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the
            `GM </maptool/index.php?title=GM&action=edit&redlink=1>`__
            notes of the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setGMNotes(notes)

               #. .. code-block:: none

                     setGMNotes(notes, id)

               #. .. code-block:: none

                     setGMNotes(notes, id, mapname)

         **Parameter**

         -  ``notes`` - The GM notes to set on the token.
         -  ``id`` - The token ``id`` of the token to set the GM notes
            on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setGMNotes&oldid=7538"

