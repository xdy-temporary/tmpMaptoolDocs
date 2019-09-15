==============================
isFunctionDefined - MapToolDoc
==============================

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

   .. rubric:: isFunctionDefined
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 isFunctionDefined()
               Function <#isFunctionDefined.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: isFunctionDefined() Function
            :name: isfunctiondefined-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Checks if a function has been defined using
            `defineFunction() <defineFunction>`__. Returns
            ``true``\ (``1``) if it has, or ``false``\ (``0``) if it has
            not. Returns '2' if the entered function is a built-in
            MapTool function rather than a user-defined function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isFunctionDefined(name)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: isFunctionDefined("fizzlegwip")]

            Returns 0.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: defineFunction("myNewFunction", "myMacro@token")]

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: isFunctionDefined("myNewFunction")]

            Returns 1.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: isFunctionDefined("input")]

            Returns 2.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() <defineFunction>`__,
            `arg() <arg>`__,
            `argCount() <argCount>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isFunctionDefined&oldid=4384"

