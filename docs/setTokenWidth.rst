==========================
setTokenWidth - MapToolDoc
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

   .. rubric:: setTokenWidth
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

            -  `1 setTokenWidth()
               Function <#setTokenWidth.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setTokenWidth() Function
            :name: settokenwidth-function

         .. container:: template_version

            • **Introduced in version 1.3b91**

         .. container:: template_description

            Sets the token's image width in pixels (boundary size).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenWidth(size)

               #. .. code-block:: none

                     setTokenWidth(size, id)

               #. .. code-block:: none

                     setTokenWidth(size, id, mapname)

         **Parameters**

         -  ``size`` - grid size of the token
         -  ``id`` - The token ``id`` of the token to set its width.
            Defaults to the `Current
            token </maptool/index.php?title=Current_token&action=edit&redlink=1>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: setTokenWidth(300, "Dragon")]

                  #. .. code-block:: none

                        [r: setTokenHeight(150, "Dragon")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setTokenHeight() <setTokenHeight>`__,
            `getTokenHeight() <getTokenHeight>`__,
            `getTokenWidth() <getTokenWidth>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenWidth&oldid=7529"

