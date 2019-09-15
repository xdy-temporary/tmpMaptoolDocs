==========================
setBarVisible - MapToolDoc
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

   .. rubric:: setBarVisible
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

         .. rubric:: setBarVisible() Function
            :name: setbarvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b46**

         .. container:: template_description

            Sets if the specified
            `bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
            for the `Current Token <Current_Token>`__ is
            visible or not. If the value is non zero then the
            `bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
            is visible, if it is 0 it is not visible.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setBarVisible(name, value)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Make "health"
            `bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
            for the `Current Token <Current_Token>`__
            visible.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setBarVisible("health", 1)]

            Hide "health"
            `bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
            for the `Current Token <Current_Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setBarVisible("health", 0)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setBarVisible&oldid=2849"

