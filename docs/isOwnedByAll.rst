=========================
isOwnedByAll - MapToolDoc
=========================

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

   .. rubric:: isOwnedByAll
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
            | ** This article needs:** *Examples using new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 isOwnedByAll()
               Function <#isOwnedByAll.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: isOwnedByAll() Function
            :name: isownedbyall-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if a
            `Token </rptools/wiki/Token>`__ has the `Owned by
            All </maptool/index.php?title=Owned_by_All&action=edit&redlink=1>`__
            check box checked.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isOwnedByAll()

               #. .. code-block:: none

                     isOwnedByAll(id)

               #. .. code-block:: none

                     isOwnedByAll(id, mapname)

         **Parameter**

         -  ``id`` - The token ``id`` of the token which has its `Owned
            by
            All </maptool/index.php?title=Owned_by_All&action=edit&redlink=1>`__
            status checked, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Returns ``Anyone can edit me`` if the `Current
            Token </rptools/wiki/Current_Token>`__ has the `Owned by
            All </maptool/index.php?title=Owned_by_All&action=edit&redlink=1>`__
            check box checked.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r, if(isOnwedByAll()): "Anyone can edit me"]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getOwners() </rptools/wiki/getOwners>`__,
            `isOwner() </rptools/wiki/isOwner>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isOwnedByAll&oldid=7504"

