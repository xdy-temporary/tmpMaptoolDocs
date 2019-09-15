=====================
getImage - MapToolDoc
=====================

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

   .. rubric:: getImage
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

            -  `1 getImage() Function <#getImage.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getImage() Function
            :name: getimage-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the `asset
            id </maptool/index.php?title=asset_id&action=edit&redlink=1>`__
            for the image of a `Token <Token>`__ or `Image
            Token <Image_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: template_clarify

            | **Needs Clarification:**
            | There's no real parameter description.
            | Error handling on duplicates should be pointed out.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getImage(name)

         **Note:** Token ID does NOT work, only token name works.

         Note that token images can be retrieved from ANY map (so they
         do NOT have to be on the current map). If identical token names
         appear on multiple maps, it may be difficult (or impossible) to
         select a specific token image using this function.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the image from an `image
            token <Token:image_token>`__ called
            ``image:Map`` you can do the following:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src="[r: getImage('image:Map')]"></img>

            Alternatively this can be used to retrieve a normal token:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src="[r: getImage('Dragon')]"></img>

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenImage <getTokenImage>`__ (which you
            can give the size as parameter)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getImage&oldid=6083"

