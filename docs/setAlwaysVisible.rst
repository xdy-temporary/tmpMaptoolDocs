=============================
setAlwaysVisible - MapToolDoc
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

   .. rubric:: setAlwaysVisible
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

         .. rubric:: setAlwaysVisible() Function
            :name: setalwaysvisible-function

         .. container:: template_version

            • **Introduced in version 1.4.2.0**

         .. container:: template_description

            Turns the corresponding setting for the token on or off.
            **Always Visible** is a VBL setting which can be found in
            the **Edit...** menu of the token under the VBL tab.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setAlwaysVisible(value, [id])

         **Parameters**

         -  ``value`` - The value of the setting to set,
            ``true``\ (``1``) or ``false``\ (``0``).
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set this setting, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setAlwaysVisible(1)]

                  #. .. code-block:: none

                        [h: setAlwaysVisible(0, "Dragon")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setAlwaysVisible&oldid=7227"

