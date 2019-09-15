======================
getTokenX - MapToolDoc
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

   .. rubric:: getTokenX
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

            -  `1 getTokenX() Function <#getTokenX.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getTokenX() Function
            :name: gettokenx-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the X coordinate of a token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenX()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenX(units)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenX(units, id)

         **Parameters**

         -  ``units`` - If set to ``false``\ (``0``), the coordinate is
            a location on the grid in number of *cells*. Defaults to
            ``true``\ (``1``), where the coordinate is in *number of
            Pixels* (in other words 0:distance in cells, 1: distance in
            pixels)'.
         -  ``id`` - The id of the token to move, defaults to the
            `Current Token </rptools/wiki/Current_Token>`__.

         **Which coordinate is returned for tokens larger then one
         cell**

         .. container:: template_proposed

            |  **Note: This refers to a proposed change that has not
              been implemented in the main code base yet.**
            | ** Details:**
            | *The ∗ marked exception will disappear.*

         -  With the exception of

         ∗ one case the coordinates of the cell are given where the
         UPPER LEFT CORNER of the the image of the token is in at that
         moment.

         -  

         ∗ The exception to this is when the token is 'Freesize' AND
         'Snapped to Grid' AND **NOT** 'On Background Layer'. In that
         particular case the coordinates of the cell where the upper
         left corner of the FOOTPRINT (NOT image) of the token is at.
         The footprint can be recognized when you move the token on the
         Token layer, it will leave the white marker on the field. The
         footprint can be the same size as the image and it is if a
         preset size is used. With freesize however the size of the
         footprint is either the original size of the image OR when you
         have used a preset (e.g. 'large') it will have the size of the
         preset as footprint.

         -  Note that if you rotate the image such that the image is no
            longer in the upper left corner, the upper left corner of
            its **native position** is still returned as its coordinate.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Moves the `Current Token </rptools/wiki/Current_Token>`__
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

            Moves the `Current Token </rptools/wiki/Current_Token>`__
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

            `moveToken() </rptools/wiki/moveToken>`__,
            `getTokenY() </rptools/wiki/getTokenY>`__,
            `getZoom() </rptools/wiki/getZoom>`__,

            `setZoom() </rptools/wiki/setZoom>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenX&oldid=6335"

