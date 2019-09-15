=============================
getMacroLocation - MapToolDoc
=============================

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

   .. rubric:: getMacroLocation
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

            -  `1 getMacroLocation()
               Function <#getMacroLocation.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getMacroLocation() Function
            :name: getmacrolocation-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the location of the macro being executed, the return
            value will be ``"chat"``, ``"global"``, ``"campaign"`` or
            the label of the token the macro resides on (e.g.
            ``"Lib:Utilities"`` or ``"Token:Orc"``.) Standard PC and NPC
            tokens will have their label prefixed with ``Token:``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroLocation()

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: MacroLocation = getMacroLocation()]

                  #. .. code-block:: none

                        [if(MacroLocation == "chat", "You are running from chat", "You are running from "+MacroLocation]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Now accurately reports where the macro
               button resides.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacroLocation&oldid=3501"

