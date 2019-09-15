=================================
herolab.getStatBlock - MapToolDoc
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

   .. rubric:: herolab.getStatBlock
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

            -  `1 herolab.getStatBlock()
               Function <#herolab.getStatBlock.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: herolab.getStatBlock() Function
            :name: herolab.getstatblock-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Returns associated statblock for the token as a string.
            Currently, Hero Lab stores three types of statblocks: Text,
            HTML, & XML.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.getStatBlock(type)

               #. .. code-block:: none

                     herolab.getStatBlock(type,id)

         Note: The different formats may or may not contain the same
         information but it does reflects what is stored in the
         portfolio. If you find missing information, in the XML
         statblock for instance, you will need to report that to [`Wolf
         Lair <http://www.wolflair.com/index.php?context=hero_lab&page=support>`__].

         **Parameters**

         -  ``type`` - A string containing either "text", "html", or
            "xml"
         -  ``id`` - The ID of the token. Defaults to the Current Token.

         Returns *HeroLab data does not exist for this token* if no data
         exists for the token and aborts the macro.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the Hero Lab Master character name associated with the
            current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [herolab.getStatBlock("text")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                         

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
         "http://lmwcs.com/maptool/index.php?title=herolab.getStatBlock&oldid=7178"

