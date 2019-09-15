=====================
getState - MapToolDoc
=====================

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

   .. rubric:: getState
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
            | ** This article needs:** *Examples using current
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getState() Function <#getState.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getState() Function
            :name: getstate-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Checks whether the specified `State </rptools/wiki/State>`__
            is active on a token, returning ``true``\ (``1``) or
            ``false``\ (``0``).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  getState(state)
                  getState(state, id)
                  getState(state, id, mapname)

         **Parameters**

         -  ``state`` - The name of the state to check for.
         -  ``id`` - The token ``id`` of the token to check for the
            state. Defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [if(getState("Dead"), "You are dead!", "You are not dead (yet!)")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `State </rptools/wiki/State>`__,
            `setState() </rptools/wiki/setState>`__,
            `setAllStates() </rptools/wiki/setAllStates>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getState&oldid=7474"

