=====================
setState - MapToolDoc
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

   .. rubric:: setState
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
            | ** This article needs:** *Examples using new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setState() Function <#setState.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setState() Function
            :name: setstate-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Sets the value of the `State </rptools/wiki/State>`__ on
            `Token </rptools/wiki/Token>`__. If The value is
            ``false``\ (``0``) then the `State </rptools/wiki/State>`__
            is unset if it is non-zero(\ ``true``\ (``1``)) then it is
            set.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setState(state, value)

               #. .. code-block:: none

                     setState(state, value, id)

               #. .. code-block:: none

                     setState(state, value, id, mapname)

         **Parameters**

         -  ``state`` - The name of the state to set on the token.
         -  ``value`` - The value of the state to set, ``true``\ (``1``)
            or ``false``\ (``0``).
         -  ``id`` - The ``id`` of the token to have the
            `State </rptools/wiki/State>`__ set. Defaults to the
            `Current Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To set the "Dead" `Token
            State </rptools/wiki/Token:state>`__ on the `Current
            Token </rptools/wiki/Current_Token>`__

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setState("Dead", 1)]

            To reset the "Dead" `Token
            State </rptools/wiki/Token:state>`__ on the `Current
            Token </rptools/wiki/Current_Token>`__

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setState("Dead", 0)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `State </rptools/wiki/State>`__,
            `getState() </rptools/wiki/getState>`__,

            `setAllStates() </rptools/wiki/setAllStates>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setState&oldid=7471"

