=============================
exposePCOnlyArea - MapToolDoc
=============================

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

   .. rubric:: exposePCOnlyArea
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

         .. rubric:: exposePCOnlyArea() Function
            :name: exposepconlyarea-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b76**

         .. container:: template_description

            Clears Fog of War (FOW) where PC tokens can see and
            establishes/restores FOW everywhere they cannot. This works
            the same as the hotkey Meta-Shift-O. Note that the keystroke
            may be different for locales other than U.S. English. This
            function is often used in combination with the
            `onTokenMove <onTokenMove>`__ event.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  exposePCOnlyArea()
                  exposePCOnlyArea(mapname)

         **Parameters**

         -  ``mapname`` - Optional map name

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Expose areas that can be seen by PC tokens on current map. -->

                  #. .. code-block:: none

                        [h: exposePCOnlyArea()]

                  #. .. code-block:: none

                        <!-- Expose areas that can be seen by PC tokens on named map. -->

                  #. .. code-block:: none

                        [h: exposePCOnlyArea("Cliffs of Insanity")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=exposePCOnlyArea&oldid=7457"

