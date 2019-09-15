========================
getNewRolls - MapToolDoc
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

   .. rubric:: getNewRolls
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

            -  `1 getNewRolls()
               Function <#getNewRolls.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getNewRolls() Function
            :name: getnewrolls-function

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Returns an array of all the raw, i.e. unmodified, dice rolls
            since the last call to **getNewRolls()**.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getNewRolls()

         **Parameters**

         -  ``none`` - Takes no parameters.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Make some dice rolls and show the individual rolls at each
            step.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 1d10: [e: 1D10+2]<br>

                  #. .. code-block:: none

                        Get New Rolls: [r: getNewRolls()]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]<br>

                  #. .. code-block:: none

                        Roll 3d6 minimum 2: [e: 3D6L2]<br>

                  #. .. code:: de2

                        Get New Rolls: [r: getNewRolls()]<br>

                  #. .. code-block:: none

                        Get Rolled: [r: getRolled()]

            **Output:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                         Roll 1d10: « 1D10+2 = 3 + 2 = 5 »

                  #. .. code-block:: none

                         Get New Rolls: [3]

                  #. .. code-block:: none

                         Get Rolled: [3]

                  #. .. code-block:: none

                         Roll 3d6 minimum 2: « 3D6L2 = 10 »

                  #. .. code:: de2

                         Get New Rolls: [5,3,1]

                  #. .. code-block:: none

                         Get Rolled: [3,5,3,1]

            Remember that it returns all the new die rolls since the
            last time it was called.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 1: [e: 3d6]<br>

                  #. .. code-block:: none

                        [r: getNewRolls()]<br>

                  #. .. code-block:: none

                        Roll 2: [e: 3d6]<br>

                  #. .. code-block:: none

                        Roll 3: [e: 3d6]<br>

                  #. .. code:: de2

                        [r: getNewRolls()]

            **Output**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Roll 1: « 3d6 = 16 »

                  #. .. code-block:: none

                        [5,6,5]

                  #. .. code-block:: none

                        Roll 2: « 3d6 = 17 »

                  #. .. code-block:: none

                        Roll 3: « 3d6 = 6 »

                  #. .. code:: de2

                        [5,6,6,3,2,1]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `clearRolls() <clearRolls>`__
            `getRolled() <getRolled>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getNewRolls&oldid=7404"

