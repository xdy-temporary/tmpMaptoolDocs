====================
getHalo - MapToolDoc
====================

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

   .. rubric:: getHalo
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

            -  `1 getHalo() Function <#getHalo.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getHalo() Function
            :name: gethalo-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Gets the color value of a token's
            `Halo <Halo>`__. The value returned is a
            string that represents the hexadecimal value of the color of
            the `Halo <Halo>`__ in the format
            ``"#RRGGBB"`` or ``"None"`` if the token has no
            `Halo <Halo>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getHalo()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getHalo(id)

         **Parameter**

         -  ``id`` - The token ``id`` of the token which has its halo
            color returned, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following example will display the text "Halo Color
            Text" in the color of the `Current
            Token <Current_Token>`__'s
            `Halo <Halo>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <span style="color:[r: getHalo()]">Halo Color Text</span>

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Halo <Halo>`__,
            `setHalo() <setHalo>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getHalo&oldid=2474"

