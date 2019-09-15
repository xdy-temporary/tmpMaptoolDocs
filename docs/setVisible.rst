=======================
setVisible - MapToolDoc
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

   .. rubric:: setVisible
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

            -  `1 setVisible() Function <#setVisible.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 See Also <#See_Also>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setVisible() Function
            :name: setvisible-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Sets the `Visible to
            Players </maptool/index.php?title=Visible_to_Players&action=edit&redlink=1>`__
            flag on a `Token </rptools/wiki/Token>`__ if the value
            passed in is non-zero(\ ``true``\ (``1``)), otherwise resets
            it to ``false``\ (``0``). The `Visible to
            Players </maptool/index.php?title=Visible_to_Players&action=edit&redlink=1>`__
            flag has two meanings, on a normal
            `Token </rptools/wiki/Token>`__ players will only be able to
            see the `Token </rptools/wiki/Token>`__ if it is set (when
            all other things like `Fog of
            War </maptool/index.php?title=Fog_of_War&action=edit&redlink=1>`__
            etc are taken into account). If it is a `Library
            Token </rptools/wiki/Library_Token>`__ then it determines if
            players can call
            `Category:Macros </rptools/wiki/Category:Macro>`__ using the
            `[macro(...):
            ...] </rptools/wiki/Macros:Branching_and_Looping>`__ roll
            option.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setVisible(visible)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setVisible(visible, id)

         **Parameters**

         -  ``visible`` - The state of visibility, ``true``\ (``1``) or
            ``false``\ (``0``).
         -  ``id`` - The token ``id`` of the token which has its player
            visibility set, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getVisible() </rptools/wiki/getVisible>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setVisible&oldid=4329"

