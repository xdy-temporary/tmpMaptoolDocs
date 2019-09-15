=============================
getTokenRotation - MapToolDoc
=============================

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

   .. rubric:: getTokenRotation
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

            -  `1 getTokenRotation()
               Function <#getTokenRotation.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenRotation() Function
            :name: gettokenrotation-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Retrieves the angle of rotation for the token from the
            default position. Returned value is in degrees.
            For Square, Round or Figure token types, this is the change
            in the facing indicator from the default of 0 degrees or no
            change in facing. Positive is CW and negative is CCW. Values
            will range from -270 to +85.

            For Top Down tokens, this is the rotation of the token image
            itself from the default of 0 degrees.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenRotation()

               #. .. code-block:: none

                     getTokenRotation(id)

               #. .. code-block:: none

                     getTokenRotation(id, mapname)

         **Parameters**

         -  ``id`` - The token id of the token to retrieve the rotation
            angle. Defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | **Result**
         | The function returns the token's rotation as a numeric value
           measured in degrees.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the rotation for the four tokens shown below.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: switchToken("Mage")]

                  #. .. code-block:: none

                        [r: token.name] - [r: r = getTokenRotation()]<br>

                  #. .. code-block:: none

                        [h: switchToken("Elf")]

                  #. .. code-block:: none

                        [r: token.name] - [r: r = getTokenRotation()]<br>

                  #. .. code:: de2

                        [h: switchToken("Hero")]

                  #. .. code-block:: none

                        [r: token.name] - [r: r = getTokenRotation()]<br>

                  #. .. code-block:: none

                        [h: switchToken("Troll")]

                  #. .. code-block:: none

                        [r: token.name] - [r: r = getTokenRotation()]

            Returns:

            |getTokenRotation.png|

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenFacing </rptools/wiki/getTokenFacing>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenRotation&oldid=7520"

