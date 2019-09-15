==========================
getMapVisible - MapToolDoc
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

   .. rubric:: getMapVisible
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

         .. rubric:: getMapVisible() Function
            :name: getmapvisible-function

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Returns ``true``\ (``1``) or ``false``\ (``0``) indicating
            whether the specified map is visible to players. If no map
            is specified the current map is selected.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMapVisible()

               #. .. code-block:: none

                     getMapVisible(mapName)

         **Parameters**

         -  ``mapName`` - Optional. A string containing the name of the
            Map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:getMapVisible()]

                  #. .. code-block:: none

                        [r:getMapVisible("Grasslands")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMapVisible&oldid=6693"

