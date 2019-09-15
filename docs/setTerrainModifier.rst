===============================
setTerrainModifier - MapToolDoc
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

   .. rubric:: setTerrainModifier
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

            -  `1 setTerrainModifier()
               Function <#setTerrainModifier.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setTerrainModifier() Function
            :name: setterrainmodifier-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Set the Terrain Modifier for the named Token or for the
            Current Token if no name is given.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTerrainModifier(mod)

               #. .. code-block:: none

                     setTerrainModifier(mod, token)

         **Parameters**

         -  ``mod`` - A floating point number.
         -  ``token`` - Optional token name.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Set the Terrain Modifier to 2.0 for the current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: tmod = setTerrainModifier(2.0)]

            **Returns:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        2.0

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTerrainModifier() </rptools/wiki/getTerrainModifier>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTerrainModifier&oldid=7416"

