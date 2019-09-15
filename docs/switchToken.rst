========================
switchToken - MapToolDoc
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

   .. rubric:: switchToken
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

         .. rubric:: switchToken() Function
            :name: switchtoken-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Changes the `Current Token <Current_Token>`__
            for the remainder of the Macro.
            In practice, "the remainder of the Macro" is the same as the
            variable scope. Thus, if a macro is running as a user
            defined function (see
            `defineFunction() <defineFunction>`__ ) with a
            new scope, switchToken will only apply until the end of the
            current macro. Once control passes back to the calling
            macro, the `Current Token <Current_Token>`__
            reverts back to what it was before the external macro was
            called ( as a function ). If a
            `defineFunction() <defineFunction>`__ does not
            create a new variable scope for the called macro, then
            effects of switchToken persist when control passes back to
            the calling macro.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     switchToken(tokenId)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=switchToken&oldid=5623"

