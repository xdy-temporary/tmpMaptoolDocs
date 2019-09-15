=================================
getMaxRecursionDepth - MapToolDoc
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

   .. rubric:: getMaxRecursionDepth
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

            -  `1 getMaxRecursionDepth()
               Function <#getMaxRecursionDepth.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getMaxRecursionDepth() Function
            :name: getmaxrecursiondepth-function

         .. container:: template_version

            • **Introduced in version 1.4.0.2**

         .. container:: template_description

            Returns the max amount of recursive calls that are allowed.
            However The recursion depth of the parser is not quite
            straight forward, there are actually two different recursion
            depths that track two different types of recursive calls,
            you can have up to 150 of each, the getRecursionDepth() will
            return the greater of the two levels.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMaxRecursionDepth()

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getMaxRecursionDepth()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getRecursionDepth() <getRecursionDepth>`__,
            `setMaxRecursionDepth() <setMaxRecursionDepth>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMaxRecursionDepth&oldid=7074"

