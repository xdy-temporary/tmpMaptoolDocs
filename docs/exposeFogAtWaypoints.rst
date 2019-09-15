=================================
exposeFogAtWaypoints - MapToolDoc
=================================

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

   .. rubric:: exposeFogAtWaypoints
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

            -  `1 exposeFogAtWaypoints()
               Function <#exposeFogAtWaypoints.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: exposeFogAtWaypoints() Function
            :name: exposefogatwaypoints-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.8**

         .. container:: template_description

            Returns a string ``(Enabled/Disabled)`` indicating whether
            the **Expose Fog At Waypoints** option is set in the MapTool
            Map menu. This menu option toggles the setting for the
            currently displayed map. This setting affects when automatic
            exposure of Fog of War (FoW) will be performed after a token
            has been moved. With it enabled, FoW will only be exposed at
            any waypoints set by the user along the tokens path plus the
            stopping point. If not enabled, FoW will be exposed from
            every cell along the token's path.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     exposeFogAtWaypoints()

         **Parameters** None.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: empty = exposeFogAtWaypoints()]

            **Returns:**

            -  Disabled - Option is disabled.
            -  Enabled - Option is enabled.

            .. rubric:: See Also
               :name: see-also

            .. container:: template_also

               `exposeFOW() <exposeFOW>`__,
               `toggleFoW() <toggleFoW>`__

         .. container:: printfooter

            Retrieved from
            "http://lmwcs.com/maptool/index.php?title=exposeFogAtWaypoints&oldid=7171"

