==========================
setCurrentMap - MapToolDoc
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

   .. rubric:: setCurrentMap
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

            -  `1 setCurrentMap()
               Function <#setCurrentMap.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setCurrentMap() Function
            :name: setcurrentmap-function

         .. container:: template_version

            • **Introduced in version 1.3b60**

         .. container:: template_description

            Designates the given map as the current one, allowing
            initiative to be moved from map to map.
            **WARNING:** This function changes an internal variable used
            by MapTool to keep track of which map is current and this
            change takes place immediately. However, changes to tokens
            are queued up and only occur when the macro finishes
            execution (well, sort of). The end result is that if a token
            is being modified on map "A" and your macro calls
            **setCurrentMap()** to switch to map "B", when the macro
            finishes and the token changes are executed they will be
            processing a token on map B! If there was no such token on
            map B a new one will be created, thus mysteriously
            duplicating tokens!

            Therefore, do NOT modify any token properties, states,
            names, notes, or any other token-specific values after
            calling **setCurrentMap()**. Or make sure that the first
            thing your macro does is call **setCurrentMap()** so that
            all tokens accessed later will be on the map that is current
            when the macro finishes.

            Search http://forums.rptools.net/ for ``setCurrentMap`` to
            find some discussion threads on this topic.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  setCurrentMap(mapName)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: status = input("NewMap|" + getAllMapNames() + "|Map to switch to|LIST|VALUE=STRING")]

                  #. .. code-block:: none

                        [h:abort(status)]

                  #. .. code-block:: none

                        [h:setCurrentMap(NewMap)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getAllMapNames() <getAllMapNames>`__
            `getVisibleMapNames() <getVisibleMapNames>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setCurrentMap&oldid=6694"

