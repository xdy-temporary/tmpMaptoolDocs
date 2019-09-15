========================
setTokenVBL - MapToolDoc
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

   .. rubric:: setTokenVBL
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

         .. rubric:: setTokenVBL() Function
            :name: settokenvbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.6**

         .. container:: template_description

            Sets the VBL of a token to that given in the JSON object
            parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenVBL(vbl, id)

         This function is used to attach the TOKEN VBL passed in as a
         JSON object to a token. The JSON object may be be created by
         calling `getTokenVBL() <getTokenVBL>`__ on a
         different token and may also be used with
         `drawVBL() <drawVBL>`__ or
         `eraseVBL() <eraseVBL>`__.

         Token VBL moves with the token, can be set under the VBL tab on
         the token edit menu and is colored YELLOW. Normal VBL is
         static, can be created with the VBL drawing tools or with the
         use of VBL functions and is colored BLUE.

         **Parameters**

         -  ``vbl`` - A JSON object containing the ``vbl`` to be added
            to the token. Use
            `getTokenVBL() <getTokenVBL>`__ to get VBL
            from another token.
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set this setting, defaults to the `Current
            Token <Current_Token>`__.

         *Example: Transfer VBL from one Token to another*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: vbl = getTokenVBL("Door, Steel")]
                  [h: setTokenVBL(vbl, "Door, Wood")]

         *Example: Erase VBL from Token*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: finalVblData = "{'shape':'none'}"]
                  [r: setTokenVBL(finalVblData)]

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking <Introduction_to_Vision_Blocking>`__
            , `getTokenVBL() <getTokenVBL>`__,
            `drawVBL() <drawVBL>`__,
            `eraseVBL() <eraseVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenVBL&oldid=7009"

