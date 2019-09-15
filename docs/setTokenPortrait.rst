=============================
setTokenPortrait - MapToolDoc
=============================

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

   .. rubric:: setTokenPortrait
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

         .. rubric:: setTokenPortrait() Function
            :name: settokenportrait-function

         .. container:: template_version

            • **Introduced in version 1.3b77**

         .. container:: template_description

            Sets the portrait image for the for the `Current
            Token </rptools/wiki/Current_Token>`__. The image can come
            from several sources. It can be an `asset
            id </maptool/index.php?title=asset_id&action=edit&redlink=1>`__
            (like from
            `tblImage() </rptools/wiki/Macros:Functions:tblImage>`__
            or\ `getTokenImage() </rptools/wiki/Macros:Functions:getTokenImage>`__.)
            or a `Image Token </rptools/wiki/Image_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenPortrait(assetId)

               #. .. code-block:: none

                     setTokenPortrait(assetId, id)

               #. .. code-block:: none

                     setTokenPortrait(assetId, id, mapname)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenPortrait(tokenImageName)

               #. .. code-block:: none

                     setTokenPortrait(tokenImageName, id)

               #. .. code-block:: none

                     setTokenPortrait(tokenImageName, id, mapname)

         **Parameters**

         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set the portrait, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenPortrait&oldid=7483"

