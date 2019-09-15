=================
eval - MapToolDoc
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

   .. rubric:: eval
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

            -  `1 eval() Function <#eval.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: eval() Function
            :name: eval-function

         .. container:: template_version

            • **Introduced in version pre-1.3**

         .. container:: template_description

            Evaluates an expression in a string and returns the result.
            The string contains the same type of expression that is
            usually located between macro brackets (e.g **{ }** or **[r:
            2+2]**). **eval()** is commonly used to evaluate dynamically
            built `input() </rptools/wiki/input>`__ parameters, or dice
            expressions stored in token properties. For more complex
            evaluation functions, see
            `evalMacro() </rptools/wiki/evalMacro>`__ and
            `execMacro() </rptools/wiki/execMacro>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     eval(expr)

         **Parameter**

         -  ``expr`` - A string containing the expression to be
            evaluated.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: eval("1+1")]

            Returns ``2``

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: eval("3d6")]

            Returns a random number from ``3`` to ``18``.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: eval("TestVar = 2")]

            Returns ``2``

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: TestVar = 2][r: eval("TestVar/2")]

            Returns ``1``

            | 
            | **Tip** Since ``eval()`` only accepts strings as parameter
              and it happens quite often that you have either numbers or
              strings following code is a good method to make it work in
              any case.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: foo = eval(string(bar))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `evalMacro() </rptools/wiki/evalMacro>`__,
            `execMacro() </rptools/wiki/execMacro>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=eval&oldid=4282"

