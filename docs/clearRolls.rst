=======================
clearRolls - MapToolDoc
=======================

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

   .. rubric:: clearRolls
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

            -  `1 clearRolls() Function <#clearRolls.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: clearRolls() Function
            :name: clearrolls-function

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Clears the internal array that keeps track of the individual
            dice rolls for the current macro.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     clearRolls()

         **Parameters**

         -  ``none`` - Takes no parameters.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Clear the saved rolls after second time.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 3d6: [e: 3D6]<br>

                  #. .. code-block:: none

                        Get New Rolls: [r: getNewRolls()]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]<br>

                  #. .. code-block:: none

                        Roll 3d6 minimum 2: [e: 3D6L2]<br>

                  #. .. code:: de2

                        Get New Rolls: [r: getNewRolls()]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]<br>

                  #. .. code-block:: none

                        -- Clear Rolls --[h: clearRolls()]<br>

                  #. .. code-block:: none

                        Roll 3d6: [e: 3D6]<br>

                  #. .. code-block:: none

                        Get New Rolls: [r: getNewRolls()]<br>

                  #. .. code:: de2

                        Get Rolled: [r: getRolled()]<br>

            **Output:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 3d6: « 3D6 = 12 »

                  #. .. code-block:: none

                        Get New Rolls: [5,5,2]

                  #. .. code-block:: none

                        Get Rolled: [5,5,2]

                  #. .. code-block:: none

                        Roll 3d6 minimum 2: « 3D6L2 = 17 »

                  #. .. code:: de2

                        Get New Rolls: [5,6,6]

                  #. .. code-block:: none

                        Get Rolled: [5,5,2,5,6,6]

                  #. .. code-block:: none

                        -- Clear Rolls --

                  #. .. code-block:: none

                        Roll 3d6: « 3D6 = 8 »

                  #. .. code-block:: none

                        Get New Rolls: [2,2,4]

                  #. .. code:: de2

                        Get Rolled: [2,2,4]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getNewRolls() <getNewRolls>`__
            `getRolled() <getRolled>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=clearRolls&oldid=7390"

