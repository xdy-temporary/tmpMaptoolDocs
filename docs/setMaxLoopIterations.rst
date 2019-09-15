=================================
setMaxLoopIterations - MapToolDoc
=================================

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

   .. rubric:: setMaxLoopIterations
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

            -  `1 setMaxLoopIterations()
               Function <#setMaxLoopIterations.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setMaxLoopIterations() Function
            :name: setmaxloopiterations-function

         .. container:: template_version

            • **Introduced in version 1.4.0.2**

         .. container:: template_description

            Sets the max amount of loops (in
            `[count():] </rptools/wiki/count_(roll_option)>`__,
            `[foreach():] </rptools/wiki/foreach_(roll_option)>`__,
            `[for():] </rptools/wiki/for_(roll_option)>`__,
            `[while():] </rptools/wiki/while_(roll_option)>`__) that are
            allowed. The current allowed max is 10,000 and this is also
            the minimum. Note that this settings lasts only for the
            current session.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMaxLoopIterations(numLoops)

         Where

         -  *numLoops* is the new maximum allowed iterations, this value
            cannot be lower than 10,000

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: setMaxLoopIterations()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getMaxLoopIterations() </rptools/wiki/getMaxLoopIterations>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setMaxLoopIterations&oldid=6842"

