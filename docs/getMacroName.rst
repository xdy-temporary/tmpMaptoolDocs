=========================
getMacroName - MapToolDoc
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

   .. rubric:: getMacroName
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

         .. rubric:: getMacroName() Function
            :name: getmacroname-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the name of the macro being executed via
            `[macro():] </rptools/wiki/macro_(roll_option)>`__ . If the
            macro typed into chat, run by clicking on a `macro
            button </rptools/wiki/Macro_Button>`__, or run via the
            `token popup
            menu </maptool/index.php?title=Token:popup_menu&action=edit&redlink=1>`__
            then this function will return "chat".

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroName()

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: macroName = getMacroName()]

                  #. .. code-block:: none

                        [if(macroName == "chat", "You are running from chat", "You are running the macro called " + macroName)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacroName&oldid=5584"

