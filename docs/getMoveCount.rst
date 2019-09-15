=========================
getMoveCount - MapToolDoc
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

   .. rubric:: getMoveCount
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

         .. rubric:: getMoveCount() Function
            :name: getmovecount-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b76**

         .. container:: template_description

            Returns the token's last movement count in units. The count
            takes movement metric into account, and thus works on
            gridless, hex, and square grids. Two optional parameters
            allow you to set the function to return true/false (1/0) if
            there was fractional movement left over and the second
            toggles whether Terrain Modifiers for determining returned
            movement count.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  getMoveCount()
                  getMoveCount(fractionOnly)
                  getMoveCount(fractionOnly,useTerrainMods)

         **Parameters**

         -  ``fractionOnly`` - 0 for normal count (default); 1 for
            fractional movement - only valid with 1-2-1 movement metric
         -  ``useTerrainMods`` - 0 to ignore terrain modifiers when
            determining movement count; 1 to account for terrain
            modifiers (default)

         **Fraction Only** - Return value will be a 0 when there was an
         even number of diagonal movements and 1 for an odd number. This
         should only be used with the ONE-TWO-ONE movement metric.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.0** - Added Fraction Only and Use Terrain Modifiers
               parameters.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMoveCount&oldid=7447"

