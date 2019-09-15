============================
getTokenHandout - MapToolDoc
============================

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

   .. rubric:: getTokenHandout
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

            -  `1 getTokenHandout()
               Function <#getTokenHandout.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenHandout() Function
            :name: gettokenhandout-function

         .. container:: template_description

            Returns the `asset
            id </maptool/index.php?title=Asset_ID&action=edit&redlink=1>`__
            of the handout image for the for the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenHandout()

               #. .. code-block:: none

                     getTokenHandout(size)

               #. .. code-block:: none

                     getTokenHandout(size, id)

               #. .. code-block:: none

                     getTokenHandout(size, id, mapname)

         **Parameters**

         -  ``size`` - OPTIONAL: The size the image should be returned
            as. If a blank string "", no size adjustment is done.
            Defaults to "".
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to retrieve the token handout image, defaults to
            the `Current Token </rptools/wiki/Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the image for the current
            `Token </rptools/wiki/Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src='[r:getTokenHandout()]'></img>

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenHandout&oldid=7488"

