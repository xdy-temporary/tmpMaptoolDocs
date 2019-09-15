====================
isOwner - MapToolDoc
====================

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

   .. rubric:: isOwner
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

            -  `1 isOwner() Function <#isOwner.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: isOwner() Function
            :name: isowner-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if the given
            `Player </maptool/index.php?title=Player&action=edit&redlink=1>`__
            is an owner of a specific `Token <Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isOwner()

               #. .. code-block:: none

                     isOwner(player)

               #. .. code-block:: none

                     isOwner(player, id)

               #. .. code-block:: none

                     isOwner(player, id, mapname)

         **Parameters**

         -  ``player`` - The name of the player to check for ownership,
            defaults to the `Current
            Player </maptool/index.php?title=Current_Player&action=edit&redlink=1>`__.
         -  ``id`` - The token ``id`` of the token which is checked for
            ownership, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Returns ``You can edit me.`` if the `Current
            Player </maptool/index.php?title=Current_Player&action=edit&redlink=1>`__
            is an owner of the `Current
            Token <Current_Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r, if(isOwner()): "You can edit me."]

            Returns ``Azhrei can edit me.`` if the given
            `Player </maptool/index.php?title=Player&action=edit&redlink=1>`__
            is an owner of the given `Token <Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = getSelected() ]

                  #. .. code-block:: none

                        [r, if(isOwner("Azhrei", id)): "Azhrei can edit me."]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getOwners() <getOwners>`__,
            `isOwnedByAll() <isOwnedByAll>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isOwner&oldid=7505"

