======================
moveToken - MapToolDoc
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

   .. rubric:: moveToken
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

            -  `1 moveToken() Function <#moveToken.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: moveToken() Function
            :name: movetoken-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Move a token to a new location.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     moveToken(x, y)

               #. .. code-block:: none

                     moveToken(x, y, units)

               #. .. code-block:: none

                     moveToken(x, y, units, id)

         **Parameters**

         -  ``x`` - The X coordinate to move the token to.
         -  ``y`` - The Y coordinate to move the token to.
         -  ``units`` - If set to ``false``\ (``0``), the coordinates
            are a location on the grid in **cells**. Defaults to
            ``true``\ (``1``), where the coordinates are in *Distance
            Per Cell* **pixels**.
         -  ``id`` - The id
            `string <Macros:Variables:string>`__ of the
            token to move, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

          

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Moves the `Current Token <Current_Token>`__
            down ``5`` **units**, and left ``10`` **units**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: CurrentX = getTokenX()]

                  #. .. code-block:: none

                        [h: CurrentY = getTokenY()]

                  #. .. code-block:: none

                        [h: NewX = CurrentX + 5]

                  #. .. code-block:: none

                        [h: NewY = CurrentY - 10]

                  #. .. code:: de2

                        [h: moveToken(NewX, NewY)]

            Moves the `Current Token <Current_Token>`__
            down ``5`` **cells**, and left ``10`` **cells**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: CurrentX = getTokenX(0)]

                  #. .. code-block:: none

                        [h: CurrentY = getTokenY(0)]

                  #. .. code-block:: none

                        [h: NewX = CurrentX + 5]

                  #. .. code-block:: none

                        [h: NewY = CurrentY - 10]

                  #. .. code:: de2

                        [h: moveToken(NewX, NewY, 0)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenX() <getTokenX>`__,
            `getTokenY() <getTokenY>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=moveToken&oldid=7222"

