=================================
setCurrentInitiative - MapToolDoc
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

   .. rubric:: setCurrentInitiative
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

         .. rubric:: setCurrentInitiative() Function
            :name: setcurrentinitiative-function

         .. container:: template_description

            Gives the
            `Initiative </maptool/index.php?title=Initiative:Initiative&action=edit&redlink=1>`__
            to the `Token </rptools/wiki/Token>`__ at the specified
            offset in the `Initiative
            Panel </maptool/index.php?title=Iniatiative:Initiative_Panel&action=edit&redlink=1>`__.
            Offsets start at 0. To clear, specify a number that is not a
            valid token offset, like -1.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: setCurrentInitiative(offset)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Give Initiative to the 4th `Token </rptools/wiki/Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setCurrentInitiative(3)]

            Clear current initiative (any number that is not a valid
            token offset will work).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setCurrentInitiative(-1)]

                  #. .. code-block:: none

                        [h: setCurrentInitiative(999)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setCurrentInitiative&oldid=5574"

