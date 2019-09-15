===============================
setTokenSnapToGrid - MapToolDoc
===============================

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

   .. rubric:: setTokenSnapToGrid
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

            -  `1 setTokenSnapToGrid()
               Function <#setTokenSnapToGrid.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setTokenSnapToGrid() Function
            :name: settokensnaptogrid-function

         .. container:: template_version

            • **Introduced in version 1.4**

         .. container:: template_description

            Sets the "snap to" behaviour for the `Current
            Token <Current_Token>`__ or a specified token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenSnapToGrid(snap)

               #. .. code-block:: none

                     setTokenSnapToGrid(snap, id)

               #. .. code-block:: none

                     setTokenSnapToGrid(snap, id, mapname)

         **Parameters**

         -  ``snap`` - A value ``true``\ (``1``) or ``false``\ (``0``).
         -  ``id`` - The id of the token to set its snap behaviour.
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setTokenSnapToGrid(0)]

                  #. .. code-block:: none

                        [h: setTokenSnapToGrid(1, currentToken())]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isSnapToGrid() <isSnapToGrid>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenSnapToGrid&oldid=7539"

