======================
getRolled - MapToolDoc
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

   .. rubric:: getRolled
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

            -  `1 getRolled() Function <#getRolled.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getRolled() Function
            :name: getrolled-function

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Returns an array of all the raw, i.e. unmodified, dice rolls
            that have occurred within the current macro context.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getRolled()

         **Parameters**

         -  ``none`` - Takes no parameters.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Roll some dice and observe the unmodified rolls.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 1d10: [e: 1D10+2]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]<br>

                  #. .. code-block:: none

                        Roll 3d6 minimum 2: [e: 3D6L2]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]

            **Output:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 1d10: « 1D10+2 = 9 + 2 = 11 »

                  #. .. code-block:: none

                        Get Rolled: [9]

                  #. .. code-block:: none

                        Roll 3d6 minimum 2: « 3D6L2 = 13 »

                  #. .. code-block:: none

                        Get Rolled: [9,6,5,1]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `clearRolls() </rptools/wiki/clearRolls>`__
            `getNewRolls() </rptools/wiki/getNewRolls>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getRolled&oldid=7391"

