=============================
getTokenPortrait - MapToolDoc
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

   .. rubric:: getTokenPortrait
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

            -  `1 getTokenPortrait()
               Function <#getTokenPortrait.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__
               -  `1.4 Version Notes <#Version_Notes>`__

         .. rubric:: getTokenPortrait() Function
            :name: gettokenportrait-function

         .. container:: template_description

            Returns the `asset
            id </maptool/index.php?title=Asset_ID&action=edit&redlink=1>`__
            of the portrait image for the for the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenPortrait()

               #. .. code-block:: none

                     getTokenPortrait(size)

               #. .. code-block:: none

                     getTokenPortrait(size, id)

               #. .. code-block:: none

                     getTokenPortrait(size, id, mapname)

         **Parameters**

         -  ``size`` - OPTIONAL: The size the picture should be returned
            as. If a blank string "", no size adjustment is done.
            Defaults to "".
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to retrieve the token image, defaults to the
            `Current Token </rptools/wiki/Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To display the image for the current
            `Token </rptools/wiki/Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <img src='[r:getTokenPortrait()]'></img>

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

         .. rubric:: Version Notes
            :name: version-notes

         In versions before v1.3b51 an attempt to retrieve a portrait
         image when none was present produced an error. In 1.3b51 and
         later builds the function returns an empty string if no
         portrait is associated with the image.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenPortrait&oldid=7487"

