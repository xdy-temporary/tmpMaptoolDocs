======================
evalMacro - MapToolDoc
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

   .. rubric:: evalMacro
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
         from\ `execMacro </maptool/index.php?title=execMacro&redirect=no>`__\ )

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

            -  `1 evalMacro() Function <#evalMacro.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: evalMacro() Function
            :name: evalmacro-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Evaluates and "executes" the macro in a string and returns
            the result. The string contains the same type of macro
            commands that you would put in a token macro with the
            exception that it can not contain slash commands.
            If you are performing rolls in the macro that create tool
            tips or use ``[e: ]`` then you will have to use either
            ``{ }`` or ``[r: ]`` to display the output otherwise you
            will get incorrect formatting.

            The **evalMacro()** function executes the macro in the same
            variable scope (i.e. the executed macro can read and alter
            variables from the current macro), where as
            `execMacro() </rptools/wiki/execMacro>`__ creates a new
            variable scope (i.e. the executed macro can neither read nor
            alter varaibles from the current macro).

            The advantage of this function over
            `eval() </rptools/wiki/eval>`__ is that with
            `eval() </rptools/wiki/eval>`__ you can only give a string
            as parameter that can be evaluated (e.g. ``"3+5"``), while
            with **evalMacro()** you can give anything as parameter but
            only the parts between ``[``\ brackets\ ``]`` will be
            evaluated. (e.g. ``"Your resulting roll is [r:1d10]"``)

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     evalMacro(macroString)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     execMacro(macroString)

         **Parameter**

         -  ``macroString`` - The string containing the macro script
            that is evaluated/executed.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setNotes(evalMacro('[r,macro("CreateNotes@Lib:Notes"): ""]'))]

            Sets the Notes of a `Token </rptools/wiki/Token>`__ to the
            output of the ``CreateNotes`` macro located on the
            ``Lib:Notes`` `Library
            Token </rptools/wiki/Library_Token>`__.

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: evalMacro("[h: TestVar1 = 5][h: TestVar2 = 10][TestVar1+TestVar2]")]

            Returns ``15``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: TestVar3 = 10]

                  #. .. code-block:: none

                        [h: TestVar4 = 20]

                  #. .. code-block:: none

                        [r: evalMacro("[TestVar3+TestVar4]")]

            Returns ``30``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: TestVar3 = 15]

                  #. .. code-block:: none

                        [h: TestVar4 = 30]

                  #. .. code-block:: none

                        [h: evalMacro("[TestVar5 = TestVar3+TestVar4]")]

                  #. .. code-block:: none

                        [TestVar5]

            Returns ``45``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: TestVar6 = 20]

                  #. .. code-block:: none

                        [h: TestVar7 = 40]

                  #. .. code-block:: none

                        [r: execMacro("[TestVar6+TestVar7]")]

            Prompts for the values of ``TestVar6`` and ``TestVar7``,
            then it returns the sum of those two values.

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: TestVar8 = 50]

                  #. .. code-block:: none

                        [h: TestVar9 = 100]

                  #. .. code-block:: none

                        [h: TestVar10 = 0]

                  #. .. code-block:: none

                        [h: execMacro("[TestVar10 = TestVar8+TestVar9]")]

                  #. .. code:: de2

                        [TestVar10]

            Returns ``0``

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: evalMacro("[h:roll=1d20]You roll [r:roll] and you [r:if(roll<10, 'hit', 'miss')] your target.")]

            Returns ``You roll 3 and you hit your target.``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `eval() </rptools/wiki/eval>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=evalMacro&oldid=6288"

