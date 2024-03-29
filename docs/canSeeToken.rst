========================
canSeeToken - MapToolDoc
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

   .. rubric:: canSeeToken
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

            -  `1 canSeeToken()
               Function <#canSeeToken.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: canSeeToken() Function
            :name: canseetoken-function

         .. container:: template_version

            • **Introduced in version 1.3b77**

         .. container:: template_description

            Returns a json array of the points visible on the target
            token from the source token as an enumerated list. Default
            source is `Current Token <Current_Token>`__.
            The enumerated list will contain zero to five of the
            following values:

            -  TOP_RIGHT
            -  BOTTOM_RIGHT
            -  TOP_LEFT
            -  BOTTOM_LEFT
            -  CENTER

            When a token is not visible, an empty json array is
            returned: '[]'

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  canSeeToken(target)
                  canSeeToken(target, source)
                  canSeeToken(target, source, mapname)

         **Parameters**

         -  ``target`` - Either the token ID or name of the target
            token.
         -  ``source`` - Either the token ID or name of the source, i.e.
            viewing token.
         -  ``mapname`` - The name of the map to find the two tokens.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Dragon token partially hidden by VBL from current token. -->

                  #. .. code-block:: none

                        [r: canSeeToken("Dragon")]

                  #. .. code-block:: none

                        <!-- Troll token completely hidden from Elf token. -->

                  #. .. code-block:: none

                        [r: canSeeToken("Troll","Elf")]

                  #. .. code:: de2

                        <!-- Troll token visible to Hero token. -->

                  #. .. code-block:: none

                        [r: canSeeToken("Troll","Token")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: javascript source-javascript

                  .. code-block:: none

                     ["TOP_LEFT", "TOP_RIGHT", "CENTER"]
                     []
                     ["TOP_LEFT", "BOTTOM_LEFT", "TOP_RIGHT", "BOTTOM_RIGHT", "CENTER"]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=canSeeToken&oldid=7564"

