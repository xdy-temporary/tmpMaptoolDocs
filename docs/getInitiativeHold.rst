==============================
getInitiativeHold - MapToolDoc
==============================

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

   .. rubric:: getInitiativeHold
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getInitiativeHold() Function
            :name: getinitiativehold-function

         .. container:: template_version

            • **Introduced in version 1.3b41**

         .. container:: template_description

            Returns if the `token </rptools/wiki/Token:token>`__ is on
            `hold </maptool/index.php?title=Initiative:hold&action=edit&redlink=1>`__
            in the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__
            or not. This function will return 1 if the
            `token </rptools/wiki/Token:token>`__ is on
            `hold </maptool/index.php?title=Initiative:hold&action=edit&redlink=1>`__
            or 0 if it is not.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getInitiativeHold()

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: if(getInitiativeHold(), "You are on hold", "You are not on hold")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getInitiativeHold&oldid=1886"

