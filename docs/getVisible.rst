=======================
getVisible - MapToolDoc
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

   .. rubric:: getVisible
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getVisible() Function <#getVisible.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 See Also <#See_Also>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getVisible() Function
            :name: getvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Returns ``true``\ (``1``) if the `visible to
            players </maptool/index.php?title=Token:visible_to_players&action=edit&redlink=1>`__
            flag is set on a `Token </rptools/wiki/Token>`__ otherwise
            returns ``false``\ (``0``). The `visible to
            players </maptool/index.php?title=Token:visible_to_players&action=edit&redlink=1>`__
            flag has two meanings, on a normal
            `Token </rptools/wiki/Token>`__ players will only be able to
            see the `Token </rptools/wiki/Token>`__ if it is set (when
            all other things like `Fog of
            War </maptool/index.php?title=Map:Fog_of_War&action=edit&redlink=1>`__
            etc are taken into account). If it is a `Library
            Token </rptools/wiki/Library_Token>`__ then it determines if
            players can call Macros using
            `[macro():] </rptools/wiki/macro_(roll_option)>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisible()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisible(id)

         **Parameter**

         -  ``id`` - The token ``id`` of token that has its player
            visibility checked, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setVisible() </rptools/wiki/setVisible>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - No longer a trusted function, added ``id``
               parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getVisible&oldid=5627"

