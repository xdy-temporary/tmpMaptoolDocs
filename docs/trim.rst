=================
trim - MapToolDoc
=================

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

   .. rubric:: trim
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

            -  `1 trim() Function <#trim.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: trim() Function
            :name: trim-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a copy of the string that is passed in with the
            leading and trailing white space removed.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trim(str)

         **Parameter**

         -  ``str`` - The string that has its leading and trailing white
            space removed.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: ":" + trim("     this is a test") + ":"]

                  #. .. code-block:: none

                        [r: ":" + trim("this is a test      ") + ":"]

                  #. .. code-block:: none

                        [r: ":" + trim("     this is a test       ") + ":"]

            Returns

            ::

                  :this is a test:
                  :this is a test:

             :this is a test:

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `substring() </rptools/wiki/substring>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=trim&oldid=3350"

