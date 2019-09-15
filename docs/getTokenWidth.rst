==========================
getTokenWidth - MapToolDoc
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

   .. rubric:: getTokenWidth
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

            -  `1 getTokenWidth()
               Function <#getTokenWidth.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenWidth() Function
            :name: gettokenwidth-function

         .. container:: template_version

            • **Introduced in version 1.3b89**

         .. container:: template_description

            Retrieves the token's image width in pixels (boundary size).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenWidth()

               #. .. code-block:: none

                     getTokenWidth(id)

               #. .. code-block:: none

                     getTokenWidth(id, mapname)

         **Parameters**

         -  ``id`` - The token id of the token to check for its width,
            defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 
         | **Result**
         | The token's boundary (image) width in pixels.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Assuming a token called ``"Dragon"``, medium size, on a 50px
            square grid, then:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getTokenWidth("Dragon")]

            returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        50

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenHeight() </rptools/wiki/getTokenHeight>`__
            `getTokenNativeHeight() </rptools/wiki/getTokenNativeHeight>`__

            `getTokenNativeWidth() </rptools/wiki/getTokenNativeWidth>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenWidth&oldid=7527"

