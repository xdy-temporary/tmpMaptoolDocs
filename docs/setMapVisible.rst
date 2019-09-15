==========================
setMapVisible - MapToolDoc
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

   .. rubric:: setMapVisible
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

         .. rubric:: setMapVisible() Function
            :name: setmapvisible-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Sets a maps visibility to players to ``true``\ (``1``) or
            ``false``\ (``0``). If no map is specified the current map
            is selected.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMapVisible(visible)

               #. .. code-block:: none

                     setMapVisible(visible, mapName)

         **Parameters**

         -  ``visible`` - Whether or not the map can be seen by players,
            ``true``\ (``1``) or ``false``\ (``0``).
         -  ``mapName`` - A string containing the name of the Map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:setMapVisible(1)]

                  #. .. code-block:: none

                        [r:setMapVisible(1, "Grasslands")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setMapVisible&oldid=6700"

