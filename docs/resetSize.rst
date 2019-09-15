======================
resetSize - MapToolDoc
======================

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

   .. rubric:: resetSize
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

            -  `1 resetSize() Function <#resetSize.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: resetSize() Function
            :name: resetsize-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Resets the `Size </rptools/wiki/Size>`__ of a
            `Token </rptools/wiki/Token>`__ to the default for grid type
            of the map it occupies. See
            `setSize() </rptools/wiki/setSize>`__ for details about the
            default size for different grid types.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     resetSize()

               #. .. code-block:: none

                     resetSize(id)

               #. .. code-block:: none

                     resetSize(id, mapname)

         **Parameters**

         -  ``id`` - The token ``id`` of the token to reset, defaults to
            the `Current Token </rptools/wiki/Current_Token>`__.
         -  ``mapName`` - Optional map name to find the token. Defaults
            to current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To reset the size of the current token to the default for
            the map:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: resetSize()]

            To reset the size of token **Chocolate Moose** on map
            **Cadbury**:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: tok = "Chocolate Moose"]

                  #. .. code-block:: none

                        [h: map = "Cadbury"]

                  #. .. code-block:: none

                        [h: resetSize(tok, map)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getSize() </rptools/wiki/getSize>`__
            `setSize() </rptools/wiki/setSize>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapName`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=resetSize&oldid=7502"

