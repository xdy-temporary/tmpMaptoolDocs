==========================
setOwnedByAll - MapToolDoc
==========================

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

   .. rubric:: setOwnedByAll
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

            -  `1 setOwnedByAll()
               Function <#setOwnedByAll.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setOwnedByAll() Function
            :name: setownedbyall-function

         .. container:: template_version

            • **Introduced in version 1.4.2.0**

         .. container:: template_description

            Allows changing the **ownedByAll** value of a token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setOwnedByAll(owned)

               #. .. code-block:: none

                     setOwnedByAll(owned, id)

               #. .. code-block:: none

                     setOwnedByAll(owned, id, mapname)

         **Parameter**

         -  ``owned`` - The value of the setting to set,
            ``true``\ (``1``) or ``false``\ (``0``).
         -  ``id`` - The token ``id`` of the token which has its `Owned
            by
            All </maptool/index.php?title=Owned_by_All&action=edit&redlink=1>`__
            status set, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwnedByAll(1)]

                  #. .. code-block:: none

                        [h: setOwnedByAll(0, "Dragon")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getOwners() </rptools/wiki/getOwners>`__,
            `isOwner() </rptools/wiki/isOwner>`__,
            `isOwnedByAll() </rptools/wiki/isOwnedByAll>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setOwnedByAll&oldid=7524"

