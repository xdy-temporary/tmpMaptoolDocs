==========================
setTokenImage - MapToolDoc
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

   .. rubric:: setTokenImage
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

            -  `1 setTokenImage()
               Function <#setTokenImage.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setTokenImage() Function
            :name: settokenimage-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the image for the for the `Current
            Token <Current_Token>`__. The image can come
            from several sources. It can come from a function that
            returns an `asset
            id </maptool/index.php?title=asset_id&action=edit&redlink=1>`__
            such as
            `tblImage() <Macros:Functions:tblImage>`__ or
            `getTokenImage() <Macros:Functions:getTokenImage>`__.
            Or it could come from a `Image
            Token <Image_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenImage(assetId)

               #. .. code-block:: none

                     setTokenImage(assetId, id)

               #. .. code-block:: none

                     setTokenImage(assetId, id, mapname)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenImage(tokenImageName)

               #. .. code-block:: none

                     setTokenImage(tokenImageName, id)

               #. .. code-block:: none

                     setTokenImage(tokenImageName, id, mapname)

         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set the image, defaults to the `Current
            Token <Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setTokenImage(tblImage("elfImages", 1))]

                  #. .. code-block:: none

                        [h: setTokenImage("image:Elf-Dead")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenImage&oldid=7482"

