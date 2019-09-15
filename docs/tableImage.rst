=======================
tableImage - MapToolDoc
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

   .. rubric:: tableImage
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

            -  `1 tableImage() Function <#tableImage.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: tableImage() Function
            :name: tableimage-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Gets the image asset value from the specified
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
            If the row is not specified then the default
            `roll </maptool/index.php?title=Roll&action=edit&redlink=1>`__
            for the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            is used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     tableImage(name)

               #. .. code-block:: none

                     tableImage(name, row)

               #. .. code-block:: none

                     tableImage(name, row, size)

               #. .. code-block:: none

                     tblImage(name)

               #. .. code:: de2

                     tblImage(name, row)

               #. .. code-block:: none

                     tblImage(name, row, size)

         **Parameters**

         -  ``name`` - A string containing the name of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
         -  ``row`` - The row of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            that should have the image asset returned.
         -  ``size`` - The size the image asset returned should be. If
            the image is not square, this will be the size of the
            height.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:** Display a random image from
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            ``"tbl1"`` using default
            `roll </maptool/index.php?title=Roll&action=edit&redlink=1>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1")]'></image>

            **Example 1:** Display the first image from
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            ``"tbl1"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1", 1)]'></image>

            **Example 2:** Display one of the first four images, resized
            to ``40`` pixels tall, from ``"tbl1"``, chosed randomly:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <image src='[r: tableImage("tbl1", "1d4", 40)]'></image>

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `table() </rptools/wiki/table>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=tableImage&oldid=6718"

