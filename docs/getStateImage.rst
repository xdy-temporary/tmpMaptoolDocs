==========================
getStateImage - MapToolDoc
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

   .. rubric:: getStateImage
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

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getStateImage() Function
            :name: getstateimage-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Gets the `asset
            id </maptool/index.php?title=Asset_ID&action=edit&redlink=1>`__
            for the image of a state, the state must be one of the image
            types for this to work.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getStateImage(state)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getStateImage(state, size)

         **Parameters**

         -  ``state`` - The name of the state which has its image asset
            returned.
         -  ``size`` - The size that the state image will be resized to;
            this is the height of the final size.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the image for the "Dead" `token
            state </rptools/wiki/Token:state>`__ use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src='[r:getStateImage("Dead")]'></img>

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getStateImage&oldid=2327"

