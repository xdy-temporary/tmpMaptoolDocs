=========================
bringToFront - MapToolDoc
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

   .. rubric:: bringToFront
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

            -  `1 bringToFront()
               Function <#bringToFront.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: bringToFront() Function
            :name: bringtofront-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Adjust the z order (or draw order) of the
            `Token </rptools/wiki/Token>`__ so that is is drawn after
            all other `Tokens </rptools/wiki/Token>`__ on the same `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__,
            this has the effect of making the
            `Token </rptools/wiki/Token>`__ appear to be in front of the
            other `Tokens </rptools/wiki/Token>`__ as it will obscure
            other `Tokens </rptools/wiki/Token>`__ on the same `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__
            in the same location.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     bringToFront()

               #. .. code-block:: none

                     bringToFront(id)

               #. .. code-block:: none

                     bringToFront(id, mapname)

         **Parameter**

         -  ``id`` - The token ``id`` or name of the token to effect,
            defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Make sure that we are visible above all other tokens on the same layer -->

                  #. .. code-block:: none

                        [h: bringToFront()]

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- The Hero of the piece should always stand out -->

                  #. .. code-block:: none

                        [h: bringToFront("Hero")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `sendToBack() </rptools/wiki/sendToBack>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bringToFront&oldid=7582"

