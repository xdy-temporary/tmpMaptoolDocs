==================================
herolab.getMasterName - MapToolDoc
==================================

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

   .. rubric:: herolab.getMasterName
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

            -  `1 herolab.getMasterName()
               Function <#herolab.getMasterName.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: herolab.getMasterName() Function
            :name: herolab.getmastername-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Get basic information about the Hero Lab data associated
            with this token. Returns a JSON object containing various
            metadata about the character.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.getMasterName()

               #. .. code-block:: none

                     herolab.getMasterName(id)

         **Parameters**

         -  ``id`` - The token id of the token to name, defaults to the
            Current Token.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the Hero Lab Master character name associated with the
            character represented by the current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: myMaster = herolab.getMasterName()]

                  #. .. code-block:: none

                        [r: out = "My master's name is: " + myMaster]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: text source-text

                  #. .. code-block:: none

                        My master's name is: Fred

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
         "http://lmwcs.com/maptool/index.php?title=herolab.getMasterName&oldid=7177"

