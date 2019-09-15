======================
isVisible - MapToolDoc
======================

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

   .. rubric:: isVisible
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

         .. rubric:: isVisible() Function
            :name: isvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b69**

         .. container:: template_description

            Check whether a point on the map is visible from a token or
            not. It returns 1 is the token is visible, 0 otherwise. This
            vision is based off of the impersonated token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isVisible(x,y)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isVisible(x,y,id)

         **Parameter**

         -  ``x`` - Then tokens x coordinate. Always in map units, not
            grid .
         -  ``y`` - Then tokens x coordinate. Always in map units, not
            grid .
         -  ``id`` - The check for visibility is performed from token
            ``id``.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            A simple example for testing out ``isVisible()``. Drop the
            default tokens "Hero" and "Troll" on a map. Make sure "Hero"
            has sight (make him PC or set sight manually). You can then
            execute the following code as a campaign macro to check if
            the Hero can see the Troll.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- lets check if token1 can see token2 -->

                  #. .. code-block:: none

                        [h: token1 = "Hero"]

                  #. .. code-block:: none

                        [h: id1 = findToken(token1)]

                  #. .. code-block:: none

                         

                  #. .. code:: de2

                        [h: token2 = "Troll"]

                  #. .. code-block:: none

                        [h: id2 = findToken(token2)]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        <!-- get the map coordinates of token2 -->

                  #. .. code-block:: none

                        <!-- i want to check if the center of the occupied cell can be seen -->

                  #. .. code:: de2

                        <!-- getTokenX/Y retrieves the top-left corner, so -->

                  #. .. code-block:: none

                        <!-- in a 50 pixel grid the center is offset by 25 pixel -->

                  #. .. code-block:: none

                        [h: x = getTokenX(1, id2)+25]

                  #. .. code-block:: none

                        [h: y = getTokenY(1, id2)+25]

                  #. .. code-block:: none

                         

                  #. .. code:: de2

                        <!-- and final the check for visiblity -->

                  #. .. code-block:: none

                        [r:getName(id1)] <b>[r, if(isVisible(x,y, id1)): "can"; "cannot"]</b> see [r:getName(id2)].

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isVisible&oldid=7216"

