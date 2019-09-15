===========================
movedOverToken - MapToolDoc
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

   .. rubric:: movedOverToken
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

            -  `1 movedOverToken()
               Function <#movedOverToken.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: movedOverToken() Function
            :name: movedovertoken-function

         .. container:: template_version

            • **Introduced in version 1.3.b74**

         .. container:: template_description

            Is used to check if the location of the target ``token`` is
            in an array of cell coordinates like the one received from
            `getLastPath() </rptools/wiki/getLastPath>`__ or the
            `onTokenMove </rptools/wiki/onTokenMove>`__ event's
            ``macro.args``.  

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  movedOverToken(token)
                  movedOverToken(token, lastPath)

         **Parameters**

         -  ``token`` - The target token to compare the
         -  ``lastPath`` - Optional JSON array of coordinate pairs. If
            not supplied will use the last path of the current token.

         **Returns**

         A JSON array of cell coordinates where the moving token crossed
         the target token.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               .. code-block:: none

                  [{"x":900,"y":400},{"x":900,"y":350},{"x":900,"y":300}]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Check if the current token moved over a token called "Pit
            Trap".

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: movedOverToken("Pit Trap")]

            **Returns:** An array of coordinate pairs. In this case,
            just one.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [{"x":550,"y":250}]

            Count how many cells of caltrops the current token moved
            through.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: lastPath = getLastPath(1)]

                  #. .. code-block:: none

                        [h: locations = movedOverToken("Caltrops",lastPath)]

                  #. .. code-block:: none

                        Token moved over [r: json.length(locations)] caltrops.

            **Returns:** A count of the cells of the *Caltrops* token
            the current token moved over.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     Token moved over 3 caltrops.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getLastPath() </rptools/wiki/getLastPath>`__
            `movedOverPoints() </rptools/wiki/movedOverPoints>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=movedOverToken&oldid=7587"

