==========================
getTokenImage - MapToolDoc
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

   .. rubric:: getTokenImage
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

            -  `1 getTokenImage()
               Function <#getTokenImage.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenImage() Function
            :name: gettokenimage-function

         .. container:: template_description

            Returns the `asset
            id </maptool/index.php?title=Asset_ID&action=edit&redlink=1>`__
            of the image for the for the `Current
            Token <Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenImage()

               #. .. code-block:: none

                     getTokenImage(size)

               #. .. code-block:: none

                     getTokenImage(size, id)

               #. .. code-block:: none

                     getTokenImage(size, id, mapname)

         **Parameters**

         -  ``size`` - OPTIONAL: The size the picture should be returned
            as. If a blank string "", no size adjustment is done.
            Defaults to "".
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to retrieve the token image, defaults to the
            `Current Token <Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To display the image for the current
            `token <Token:token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src='[r:getTokenImage()]'></img>

            To get the image of any
            `token <Token:token>`__ using its id and the
            token roll option.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h, token(tokenId): imgAsset = getTokenImage()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getImage <getImage>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenImage&oldid=7486"

