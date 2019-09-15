==========================
setTokenShape - MapToolDoc
==========================

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

   .. rubric:: setTokenShape
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *No examples yet.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setTokenShape()
               Function <#setTokenShape.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setTokenShape() Function
            :name: settokenshape-function

         .. container:: template_version

            • **Introduced in version 1.3b89**

         .. container:: template_description

            Sets the token's shape (top down, circle, square, figure).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenShape(shape)

               #. .. code-block:: none

                     setTokenShape(shape, id)

               #. .. code-block:: none

                     setTokenShape(shape, id, mapname)

         **Parameters**

         -  ``shape`` - String value: ``"TOP DOWN"``, ``"CIRCLE"``,
            ``"SQUARE"``, ``"FIGURE"``.
         -  ``id`` - The token id of the token to set to a new shape,
            defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 
         | **Result**
         | The function returns the token's shape as a string value:
           ``"TOP DOWN"``, ``"CIRCLE"``, ``"SQUARE"``, ``"FIGURE"``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            On current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: newShape = "CIRCLE"]

                  #. .. code-block:: none

                        [r: setTokenShape(newShape)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Circle

            With Token ID.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: newShape = "TOP DOWN"]

                  #. .. code-block:: none

                        [h: tokenName = "Some Token"]

                  #. .. code-block:: none

                        [r: setTokenShape(newShape,tokenName)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Top down

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenShape() <getTokenShape>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenShape&oldid=7532"

