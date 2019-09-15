=======================
sendToBack - MapToolDoc
=======================

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

   .. rubric:: sendToBack
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

            -  `1 sendToBack() Function <#sendToBack.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: sendToBack() Function
            :name: sendtoback-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Adjust the z-order (or draw order) of the
            `Token </rptools/wiki/Token>`__ so that it is drawn before
            all other `Tokens </rptools/wiki/Token>`__ on the same `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__,
            this has the effect of making the Token appear to be in back
            of the other `Tokens </rptools/wiki/Token>`__ as it will be
            obscured by other `Tokens </rptools/wiki/Token>`__ on the
            same `Map
            Layer </maptool/index.php?title=Map_Layer&action=edit&redlink=1>`__
            in the same location.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     sendToBack()

               #. .. code-block:: none

                     sendToBack(id)

               #. .. code-block:: none

                     sendToBack(id, mapname)

         **Parameter**

         -  ``id`` - The token ``id`` or name of the token that has its
            z-order changed, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Sends the `Current Token </rptools/wiki/Current_Token>`__ to
            the lowest z-order.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: sendToBack()]

            Sends all of the selected tokens to the lowest z-order.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: tokens = getSelected()]

                  #. .. code-block:: none

                        [h, foreach(id, tokens, ""), code:

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                            [h: sendToBack(id)]

                  #. .. code:: de2

                        }]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `bringToFront() </rptools/wiki/bringToFront>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=sendToBack&oldid=7581"

