========================
closeDialog - MapToolDoc
========================

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

   .. rubric:: closeDialog
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

         .. rubric:: closeDialog() Function
            :name: closedialog-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Closes the specified macro dialog that was previously
            created using `[
            dialog():] <dialog_(roll_option)>`__. If the
            `dialog <dialog>`__ is not open then the
            function has no effect.

            The most common use for this function is closing a
            `dialog <dialog>`__ based from a macro that is
            run when clicking on a link or button for the
            `dialog <dialog>`__ that has no close button.

            **NOTE** In later versions of maptool (tested in b74) this
            works only for dialogs opened with
            `[dialog():] <dialog_(roll_option)>`__. Frames
            cant be closed with this. But there is a new analog function
            available for that, too. See
            `closeFrame() <closeFrame>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: closeDialog(name)]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: closeDialog("CharacterSheet")]

            Assuming a `dialog <dialog>`__ called "Name
            Entry" has been created without the input flag but
            containing a form. In the macro called when the form is
            submitted you can use the following logic to check that the
            "name" field is not blank and close the
            `dialog <dialog>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h, if(listGet(macro.args, "name")), code: {

                  #. .. code-block:: none

                            [closeDialog("Name Entry")]

                  #. .. code-block:: none

                        } ; {

                  #. .. code-block:: none

                            <!-- otherwise we would do something here to tell the user to provide a name -->

                  #. .. code:: de2

                        }]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=closeDialog&oldid=4652"

