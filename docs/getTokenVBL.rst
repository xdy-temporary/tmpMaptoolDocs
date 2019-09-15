========================
getTokenVBL - MapToolDoc
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

   .. rubric:: getTokenVBL
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

         .. rubric:: getTokenVBL() Function
            :name: gettokenvbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.6**

         .. container:: template_description

            Gets the VBL attached to a token as a JSON object.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenVBL(id)

         This macro function is used used to get a JSON object
         describing the TOKEN VBL attached to a token. The returned JSON
         object can then be used with
         `setTokenVBL() </rptools/wiki/setTokenVBL>`__,
         `drawVBL()or </rptools/wiki/drawVBL>`__
         `eraseVBL() </rptools/wiki/eraseVBL>`__.

         Token VBL is attached to and moves with the token. It can be
         set (or cleared) under the VBL tab on the Edit Token dialog and
         is colored YELLOW. Normal VBL is static, can be created with
         the VBL drawing tools or with the use of VBL functions and is
         colored BLUE.

         **Parameters**

         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to get the VBL. Defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: vbl = getTokenVBL("Door, Steel")]
                  [h: setTokenVBL(vbl, "Door, Wood")]

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking </rptools/wiki/Introduction_to_Vision_Blocking>`__
            , `setTokenVBL() </rptools/wiki/setTokenVBL>`__,
            `drawVBL() </rptools/wiki/drawVBL>`__ or
            `eraseVBL() </rptools/wiki/eraseVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenVBL&oldid=6978"

