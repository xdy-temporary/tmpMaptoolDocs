===========================
deselectTokens - MapToolDoc
===========================

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

   .. rubric:: deselectTokens
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

            -  `1 deselectTokens()
               Function <#deselectTokens.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: deselectTokens() Function
            :name: deselecttokens-function

         .. container:: template_version

            • **Introduced in version 1.3b68**

         .. container:: template_description

            Deselects one or more visible tokens on the map.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     deselectTokens()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     deselectTokens(id)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     deselectTokens(tokens, delim)

         **Parameter**

         -  ``id`` - the id string or name of a specific token to
            deselect (the examples below use the token name, but token
            IDs are also valid); if left blank all currently selected
            tokens are deselected.
         -  ``tokens`` - a `String List </rptools/wiki/String_List>`__
            of tokens to deselect.
         -  ``delim`` - Specifies the delimiter used in the string list
            that is supplied. If the delimiter is "json", then the value
            for ``list`` may be a `JSON
            Array </rptools/wiki/JSON_Array>`__ instead. **Note: if
            using a JSON Array or String List, ``delim`` must be
            specified.**

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To deselect a single token with the name "Adventurer":

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:deselectTokens("Adventurer")]

            To deselect a list of `Tokens </rptools/wiki/Token>`__ using
            a `String List </rptools/wiki/String_List>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:deselectTokens("Adventurer, Orc 2, Goblin 1", 0, ",")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `selectTokens() </rptools/wiki/selectTokens>`__,
            `getSelected() </rptools/wiki/getSelected>`__,

            `getSelectedNames() </rptools/wiki/getSelectedNames>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b68** - Function added.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=deselectTokens&oldid=4788"

