========================
transferVBL - MapToolDoc
========================

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

   .. rubric:: transferVBL
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

            -  `1 transferVBL()
               Function <#transferVBL.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: transferVBL() Function
            :name: transfervbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.2.0**

         .. container:: template_description

            Directly transfers VBL from token to the VBL layer if true;
            otherwise, it transfers from the VBL layer to the token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     transferVBL(value)

               #. .. code-block:: none

                     transferVBL(value, delete)

               #. .. code-block:: none

                     transferVBL(value, id)

               #. .. code-block:: none

                     transferVBL(value, delete, id)

         This function can be used to transfer TOKEN VBL to NORMAL VBL
         or vice versa. Token VBL moves with the token, can be set under
         the VBL tab on the token **Edit...** menu, and is colored
         YELLOW. Normal VBL is static, can be created with the VBL
         drawing tools, or with the use of VBL functions and is colored
         BLUE.

         **Parameters**

         -  ``value`` - The value of the setting to set:

            -  ``0`` transfer normal (blue) VBL to token (yellow) VBL
            -  ``1`` transfer token (yellow) VBL to normal (blue) VBL

         -  ``delete`` - Defines if the transferred VBL is deleted from
            the source.
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set this setting, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            *Example: Transfer VBL from Token to Map*

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:transferVBL(1, "Dragon")]
                     [h:transferVBL(0)]

            *Example: Transfer VBL from Map to current Token*

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:transferVBL(0)]

            *Example: Clear VBL from Token after transfer since 1.5.1*

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:transferVBL(1, 1)]

            *Example: Clear VBL from Token after transfer before 1.5.1*

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:transferVBL(1)]
                     [h: finalVblData = "{'shape':'none'}"]
                     [h: setTokenVBL(finalVblData)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking </rptools/wiki/Introduction_to_Vision_Blocking>`__
            , `eraseVBL() </rptools/wiki/eraseVBL>`__,
            `drawVBL() </rptools/wiki/drawVBL>`__,
            `setTokenVBL() </rptools/wiki/setTokenVBL>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.0** - new delete parameter

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=transferVBL&oldid=7436"

