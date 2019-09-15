=================================
getTokenNativeHeight - MapToolDoc
=================================

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

   .. rubric:: getTokenNativeHeight
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

            -  `1 getTokenNativeHeight()
               Function <#getTokenNativeHeight.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenNativeHeight() Function
            :name: gettokennativeheight-function

         .. container:: template_version

            • **Introduced in version 1.5.1**

         .. container:: template_description

            Retrieves the token's native image height in pixels (native
            size).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenNativeHeight()

               #. .. code-block:: none

                     getTokenNativeHeight(id)

               #. .. code-block:: none

                     getTokenNativeHeight(id, mapname)

         **Parameter**

         -  ``id`` - The token id of the token to check for its height,
            defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 
         | **Result**
         | The token's native(image) height in pixels.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Assuming a token called ``"Dragon"``, with 120px native
            image height, medium size, on a 50px square grid , then:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getTokenNativeHeight("Dragon")]

            returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        120

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenHeight() </rptools/wiki/getTokenHeight>`__
            `getTokenWidth() </rptools/wiki/getTokenWidth>`__

            `getTokenNativeWidth() </rptools/wiki/getTokenNativeWidth>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenNativeHeight&oldid=7526"

