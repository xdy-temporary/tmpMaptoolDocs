=================================
setMaxRecursionDepth - MapToolDoc
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

   .. rubric:: setMaxRecursionDepth
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

            -  `1 setMaxRecursionDepth()
               Function <#setMaxRecursionDepth.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setMaxRecursionDepth() Function
            :name: setmaxrecursiondepth-function

         .. container:: template_version

            • **Introduced in version 1.4.0.2**

         .. container:: template_description

            Returns the current amount of recursive calls that are used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMaxRecursionDepth(depth)

         Where

         -  *depth* is the new maximum allowed recursive calls. Note
            that the depth can never be lower then the default depth,
            which is 150, setting it lower will result in a depth of
            150. Setting this value higher is obviously at your own risk
            as this has a serious impact on the stack. Note that this
            settings lasts only for the current session.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setMaxRecursionDepth(200)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getRecursionDepth() </rptools/wiki/getRecursionDepth>`__,
            `getMaxRecursionDepth() </rptools/wiki/getMaxRecursionDepth>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setMaxRecursionDepth&oldid=7075"

