================================
setOwnerOnlyVisible - MapToolDoc
================================

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

   .. rubric:: setOwnerOnlyVisible
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: setOwnerOnlyVisible() Function
            :name: setowneronlyvisible-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b74**

         .. container:: template_description

            Sets the `Visible to Owners
            Only </maptool/index.php?title=Visible_to_Owners_Only&action=edit&redlink=1>`__
            flag on a `Token </rptools/wiki/Token>`__ if the value
            passed in is non-zero(\ ``true``\ (``1``)), otherwise resets
            it to ``false``\ (``0``).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setOwnerOnlyVisible(visible)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setOwnerOnlyVisible(visible, id)

         **Parameters**

         -  ``visible`` - The state of owner only visibility,
            ``true``\ (``1``) or ``false``\ (``0``).
         -  ``id`` - The token ``id`` of the token which has its owner
            only visibility set, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setVisible() </rptools/wiki/setVisible>`__,
            `getOwnerOnlyVisible() </rptools/wiki/getOwnerOnlyVisible>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setOwnerOnlyVisible&oldid=5628"

