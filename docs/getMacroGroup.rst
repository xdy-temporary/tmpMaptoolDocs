==========================
getMacroGroup - MapToolDoc
==========================

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

   .. rubric:: getMacroGroup
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getMacroGroup() Function
            :name: getmacrogroup-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the indexes of the macro buttons for the specified
            group.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroGroup(group)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroGroup(group, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroGroup(group, delim, id)

         **Parameters**

         -  ``group`` - The name of the macro group to get the macro
            button indexes from.
         -  ``delim`` - The delimiter used in the string list returned,
            defaults to ``","``. If set to ``json``, then a JSON array
            is returned.
         -  ``id`` - The id of the token that the macro group is located
            on, defaults to the current token. If the id is not
            specified, this function does not require a Trusted Macro.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacroGroup&oldid=1847"

