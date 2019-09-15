================
add - MapToolDoc
================

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

   .. rubric:: add
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `sum </maptool/index.php?title=sum&redirect=no>`__\ )

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

            -  `1 add() Function <#add.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__

                  -  `1.2.1 Strings <#Strings>`__
                  -  `1.2.2 Numbers and
                     Strings <#Numbers_and_Strings>`__

         .. rubric:: add() Function
            :name: add-function

         .. container:: template_version

            • **Introduced in version 1.3.b48**

         .. container:: template_description

            Adds number and/or strings together. If all of the arguments
            to the function are numbers then a numeric addition is
            performed, if any of the arguments are strings then all of
            the arguments are concatenated as a string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: result = add(val1, val2, ...)]

               #. .. code-block:: none

                     [h: result = sum(val1, val2, ...)]

               #. .. code-block:: none

                     [h: result = concat(val1, val2, ...)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            ====Numbers====

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: add(1,4)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        5

            | 

            .. rubric:: Strings
               :name: strings

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: add("Mary", "had", "a", "little", "lamb")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        "Maryhadalittlelamb"

            | 

            .. rubric:: Numbers and Strings
               :name: numbers-and-strings

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: add(1,"4")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        "14"

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=add&oldid=7411"

