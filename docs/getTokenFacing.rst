===========================
getTokenFacing - MapToolDoc
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

   .. rubric:: getTokenFacing
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

            -  `1 getTokenFacing()
               Function <#getTokenFacing.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenFacing() Function
            :name: gettokenfacing-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the facing angle for the specified or current token.
            Default facing is down or -90 degrees. Zero degrees is along
            the X-axis to the right.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenFacing()

               #. .. code-block:: none

                     getTokenFacing(id)

               #. .. code-block:: none

                     getTokenFacing(id, mapname)

         **Parameters**

         -  ``id`` - The id of the token to get the facing from,
            defaults to the current token.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         **Returns** The angle in degrees or ``""`` if no facing has
         been set

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: switchToken("Mage")]

                  #. .. code-block:: none

                        [r: token.name]: [r: r = getTokenFacing()]<br>

                  #. .. code-block:: none

                        [h: switchToken("Elf")]

                  #. .. code-block:: none

                        [r: token.name]: [r: r = getTokenFacing()]<br>

                  #. .. code:: de2

                        [h: switchToken("Hero")]

                  #. .. code-block:: none

                        [r: token.name]: [r: r = getTokenFacing()]<br>

                  #. .. code-block:: none

                        [h: switchToken("Troll")]

                  #. .. code-block:: none

                        [r: token.name]: [r: r = getTokenFacing()]

            | **Returns:**

            |getTokenFacing.png|

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenRotation <getTokenRotation>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenFacing&oldid=7516"

