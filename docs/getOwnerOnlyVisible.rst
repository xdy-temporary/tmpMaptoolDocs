================================
getOwnerOnlyVisible - MapToolDoc
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

   .. rubric:: getOwnerOnlyVisible
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

         .. rubric:: getOwnerOnlyVisible() Function
            :name: getowneronlyvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b74**

         .. container:: template_description

            Returns ``true``\ (``1``) if the `Visible to Owners
            Only </maptool/index.php?title=Token:Visible_to_Owners_Only&action=edit&redlink=1>`__
            flag is set on a `Token <Token>`__ otherwise
            returns ``false``\ (``0``).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getOwnerOnlyVisible()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getOwnerOnlyVisible(id)

         **Parameter**

         -  ``id`` - The token ``id`` of token that has its player
            visibility checked, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getVisible() <getVisible>`__,
            `setOwnerOnlyVisible() <setOwnerOnlyVisible>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getOwnerOnlyVisible&oldid=4635"

