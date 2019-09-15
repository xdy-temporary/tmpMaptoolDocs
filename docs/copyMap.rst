====================
copyMap - MapToolDoc
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

   .. rubric:: copyMap
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

         .. rubric:: copyMap() Function
            :name: copymap-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Creates a copy of an specified map, with the new map name.
            Returns the name of the new map.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     copyMap(existingMapName, newMapName)

         **Parameters**

         -  ``existingMapName`` - The name of the existing map you wish
            to copy.
         -  ``newMapName`` - A string containing the name of the new
            copy.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:copyMap("BaseMap","Tower")]

                  #. .. code-block:: none

                        [h:setMapVisible(1,"Tower")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=copyMap&oldid=7195"

