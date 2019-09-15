============================
herolab.refresh - MapToolDoc
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

   .. rubric:: herolab.refresh
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

            -  `1 herolab.refresh()
               Function <#herolab.refresh.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: herolab.refresh() Function
            :name: herolab.refresh-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Refresh the Hero Lab data associated with this token. This
            will update the statblock and stored images.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.refresh()

               #. .. code-block:: none

                     herolab.refresh(id)

         This function will also refresh the token's images (just like
         when the token is created). The token's base Image from the
         first image in Hero Lab, the token's Portrait from the second
         image in Hero Lab, and the tokens' Handout image from the 3rd
         image in Hero Lab.

         **Parameters**

         -  ``id`` - The id of the token. Defaults to the Current Token.

         It will return a 1 if successful, otherwise it will return a 0.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the boolean value of the refresh flag in the Hero Lab
            data.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: success = herolab.refresh()]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        0 or 1

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Hero Lab
            Integration </maptool/index.php?title=Hero_Lab_Integration&action=edit&redlink=1>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5** - Added to main MapTool build.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=herolab.refresh&oldid=7186"

