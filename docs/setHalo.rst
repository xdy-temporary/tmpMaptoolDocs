====================
setHalo - MapToolDoc
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

   .. rubric:: setHalo
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

            -  `1 setHalo() Function <#setHalo.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setHalo() Function
            :name: sethalo-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Sets the `Halo <Halo>`__ color of a
            `Token <Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setHalo(color)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setHalo(color, id)

         **Parameters**

         -  ``color`` - The color to set the
            `Halo <Halo>`__ to, valid values are:

            -  ``"Black"``
            -  ``"Green"``
            -  ``"Yellow"``
            -  ``"Orange"``
            -  ``"Red"``
            -  ``"Cyan"``
            -  ``"Magenta"``
            -  ``"White"``
            -  A hexadecimal color value in the format ``"#RRGGBB"``
            -  ``"None"``

         -  ``id`` - The token ``id`` of the token that has its
            `Halo <Halo>`__ set by this function.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To remove the `Halo <Halo>`__ from the
            `Current Token <Current_Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setHalo("None")]

            To set the `Halo <Halo>`__ for the `Current
            Token <Current_Token>`__ to red.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setHalo("Red")]

            To set the `Halo <Halo>`__ from the `Current
            Token <Current_Token>`__ to a custom color

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setHalo("#33AAFF")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Halo <Halo>`__,
            `getHalo() <getHalo>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setHalo&oldid=2465"

