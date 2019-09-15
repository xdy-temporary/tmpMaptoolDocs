==================
setPC - MapToolDoc
==================

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

   .. rubric:: setPC
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

            -  `1 setPC() Function <#setPC.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 See Also <#See_Also>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setPC() Function
            :name: setpc-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets a `Token </rptools/wiki/Token>`__ to a `PC
            Token </maptool/index.php?title=PC_Token&action=edit&redlink=1>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setPC()

               #. .. code-block:: none

                     setPC(id)

               #. .. code-block:: none

                     setPC(id, mapname)

         **Parameter**

         -  ``id`` - The token ``id`` of the token which has its PC
            status set, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isPC() </rptools/wiki/isPC>`__,
            `isNPC() </rptools/wiki/isNPC>`__,

            `setNPC() </rptools/wiki/setNPC>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setPC&oldid=7496"

