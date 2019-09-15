================================
getMacroButtonIndex - MapToolDoc
================================

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

   .. rubric:: getMacroButtonIndex
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Expanded examples of usage.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getMacroButtonIndex()
               Function <#getMacroButtonIndex.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getMacroButtonIndex() Function
            :name: getmacrobuttonindex-function

         .. container:: template_version

            • **Introduced in version 1.3b50**

         .. container:: template_description

            Returns the index of the `Token <Token>`__
            macro button that was clicked on. The macro button must have
            the auto-execute check box selected. If the macro is not
            running from a `Token <Token>`__ macro button
            then ``-1`` is returned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacroButtonIndex()

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: ind = getMacroButtonIndex()]

            If the macro is not run from an auto-execute macro button on
            a `Token <Token>`__, ``ind`` is set to ``-1``.
            Otherwise ``ind`` is set to a non-negative number which is
            the index of the button.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getMacroIndexes() <getMacroIndexes>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacroButtonIndex&oldid=2993"

