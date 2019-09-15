=========================
isSnapToGrid - MapToolDoc
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

   .. rubric:: isSnapToGrid
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

            -  `1 isSnapToGrid()
               Function <#isSnapToGrid.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: isSnapToGrid() Function
            :name: issnaptogrid-function

         .. container:: template_version

            • **Introduced in version 1.3b69**

         .. container:: template_description

            Returns ``true``\ (``1``) if a
            `Token </rptools/wiki/Token>`__ is snapped to grid or
            ``false``\ (``0``) if it is not.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isSnapToGrid()

               #. .. code-block:: none

                     isSnapToGrid(id)

               #. .. code-block:: none

                     isSnapToGrid(id, mapname)

         **Parameter**

         -  ``id`` - The token ``id`` of the token which has its
            snapToGrid status checked, defaults to the `Current
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

                        [h: snap=isSnapToGrid()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setTokenSnapToGrid() </rptools/wiki/setTokenSnapToGrid>`__

         | 
         | \|changes=

         -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isSnapToGrid&oldid=7522"

