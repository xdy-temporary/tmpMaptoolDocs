======================
setGMName - MapToolDoc
======================

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

   .. rubric:: setGMName
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

            -  `1 setGMName() Function <#setGMName.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setGMName() Function
            :name: setgmname-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Sets the GM Name of a token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setGMName(name)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setGMName(name, id)

         **Parameters**

         -  ``name`` - A string that is set as the GM Name on the token.
         -  ``id`` - The token id of the token that has its GM Name set.
            Defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Sets the GM Name of the `Current
            Token </rptools/wiki/Current_Token>`__ to ``New GM Name``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setGMName("New GM Name")]

            Sets the GM Name of all selected tokens to ``New GM Name``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: SelectedTokens = getSelected()]

                  #. .. code-block:: none

                        [h,foreach(TokenID, SelectedTokens), code:

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                        [h: setGMName("New GM Name", TokenID)]

                  #. .. code:: de2

                        }]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getGMName() </rptools/wiki/getGMName>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setGMName&oldid=3395"

