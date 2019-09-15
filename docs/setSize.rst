====================
setSize - MapToolDoc
====================

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

   .. rubric:: setSize
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

            -  `1 setSize() Function <#setSize.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setSize() Function
            :name: setsize-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the size of a `Token <Token>`__ with one
            of the defined sizes according to each Grid Type. The sizes
            can be found on the `Token
            Size <Token_Size>`__ page.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setSize(size)

               #. .. code-block:: none

                     setSize(size, id)

               #. .. code-block:: none

                     setSize(size, id, mapname)

         **Parameters**

         -  ``size`` - The `Token
            Size </maptool/index.php?title=size&action=edit&redlink=1>`__
            to set the token to.
         -  ``id`` - The token ``id`` of the token which will have its
            `Token
            Size </maptool/index.php?title=size&action=edit&redlink=1>`__
            set. Defaults to the `Current
            Token <Current_Token>`__.
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To set the size of the current token to ``Medium``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setSize("Medium")]

            To set the size of the current token to whatever string is
            stored in the macro variable **mySize**:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: mySize = "Large"]

                  #. .. code-block:: none

                        [h: setSize(mySize)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getSize() <getSize>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setSize&oldid=7559"

