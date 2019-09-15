=========================
selectTokens - MapToolDoc
=========================

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

   .. rubric:: selectTokens
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

            -  `1 selectTokens()
               Function <#selectTokens.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: selectTokens() Function
            :name: selecttokens-function

         .. container:: template_version

            • **Introduced in version 1.3b68**

         .. container:: template_description

            Selects one or more visible tokens on the map.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     selectTokens()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     selectTokens(id, add)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     selectTokens(tokens, add, delim)

         **Parameter**

         -  ``id`` - the id string or token name of a specific token to
            select (the examples below use token *names*, but IDs are
            also permitted); if left blank *all* visible tokens are
            selected.
         -  ``add`` - if the value of add is ``true(1)``, the selections
            will be added to the current set of selected tokens; if the
            value is ``false(0)`` currently selected tokens will be
            deselected before new tokens are selected. Defaults to
            false.
         -  ``tokens`` - a `String List </rptools/wiki/String_List>`__
            of tokens to select.
         -  ``delim`` - Specifies the delimiter used in the string list
            that is supplied. If the delimiter is "json", then the value
            for ``tokens`` may be a `JSON
            Array </rptools/wiki/JSON_Array>`__ instead. **Note: if
            using a JSON Array or String List, both ``add`` and
            ``delim`` must be specified.**

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To select a single token with the name "Adventurer":

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:selectTokens("Adventurer")]

            To select a list of `Tokens </rptools/wiki/Token>`__ using a
            `String List </rptools/wiki/String_List>`__, replacing the
            current selection

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:selectTokens("Adventurer, Orc 2, Goblin 1", 0, ",")]

            To select a list of `Tokens </rptools/wiki/Token>`__ using a
            `JSON Array </rptools/wiki/JSON_Array>`__, adding the
            specified tokens to the current set of selected
            `Tokens </rptools/wiki/Token>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:selectTokens("['Adventurer', 'Orc 2', 'Goblin 1']", 1, "json")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `deselectTokens() </rptools/wiki/deselectTokens>`__,
            `getSelected() </rptools/wiki/getSelected>`__,

            `getSelectedNames() </rptools/wiki/getSelectedNames>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b68** - Function added.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=selectTokens&oldid=6199"

