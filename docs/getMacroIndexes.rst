============================
getMacroIndexes - MapToolDoc
============================

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

   .. rubric:: getMacroIndexes
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: getMacroIndexes() Function
            :name: getmacroindexes-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a list of the `macro
            buttons </maptool/index.php?title=macro_buttons&action=edit&redlink=1>`__
            on the `Current Token </rptools/wiki/Current_Token>`__ that
            have the specified label. The type of the value returned
            depends on the delimiter parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroIndexes(label)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroIndexes(label, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroIndexes(label, delim, id)

         **Parameters**

         -  ``label`` - The label for the macro buttons to return.
         -  ``delim`` - The delimiter used to separate the values in the
            `String List </rptools/wiki/String_List>`__ which defaults
            to ``","`` if not specified. This function returns a `JSON
            Object </rptools/wiki/JSON_Object>`__ if ``"json"`` is
            specified.
         -  ``id`` - The token ``id`` of the token that the function is
            executed on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``"json"`` delimiter option.
            -  **1.3b51** - Added ``id`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacroIndexes&oldid=2452"

