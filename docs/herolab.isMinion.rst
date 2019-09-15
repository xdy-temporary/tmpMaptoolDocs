=============================
herolab.isMinion - MapToolDoc
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

   .. rubric:: herolab.isMinion
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

            -  `1 herolab.isMinion()
               Function <#herolab.isMinion.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: herolab.isMinion() Function
            :name: herolab.isminion-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Returns true if token is a Hero Lab *minion* character, such
            as an Eidolon or Familiar. Otherwise it returns false.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.isMinion()

               #. .. code-block:: none

                     herolab.isMinion(id)

         **Parameters**

         -  ``id`` - The id of the token. Defaults to the Current Token.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the boolean value of the isMinion flag in the Hero Lab
            data.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: isMinion = herolab.isMinion()]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        0 or 1

            This is the same as using the
            `getInfo() </rptools/wiki/getInfo>`__ function and reading
            the ``isMinion`` field.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: info = herolab.getInfo()]

                  #. .. code-block:: none

                        [r: isMinion = json.get(info,"isMinion")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        0 or 1

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
         "http://lmwcs.com/maptool/index.php?title=herolab.isMinion&oldid=7184"

