=========================
isBarVisible - MapToolDoc
=========================

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

   .. rubric:: isBarVisible
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

            -  `1 isBarVisible()
               Function <#isBarVisible.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: isBarVisible() Function
            :name: isbarvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b46**

         .. container:: template_description

            Returns ``true``\ (``1``) if the specified `Token
            Bar </maptool/index.php?title=Token_Bar&action=edit&redlink=1>`__
            on the `Current Token </rptools/wiki/Current_Token>`__ is
            visible, or ``false``\ (``0``) if it is not.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isBarVisible(bar)

         **Parameters**

         -  ``bar`` - A string that contains the name of the bar that
            has its visibility checked.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Displays ``The health bar is visible!`` if the bar named
            ``Health`` is set to visible; otherwise it displays
            ``The health bar is not visible!``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [if(isBarVisible("Health")), code:

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                            The health bar is visible!

                  #. .. code-block:: none

                        };{

                  #. .. code:: de2

                            The health bar is not visible!

                  #. .. code-block:: none

                        }]

            Toggles the visibility of the bar named ``Fatigue``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setBarVisible("Fatigue", !isBarVisible("Fatigue"))]

                  #. .. code-block:: none

                        [h: abort(0)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setBarVisible() </rptools/wiki/setBarVisible>`__,
            `getBar() </rptools/wiki/getBar>`__,

            `setBar() </rptools/wiki/setBar>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isBarVisible&oldid=3386"

