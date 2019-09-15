===================
assert - MapToolDoc
===================

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

   .. rubric:: assert
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

            -  `1 assert() Function <#assert.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Usage Notes <#Usage_Notes>`__
               -  `1.4 See Also <#See_Also>`__
               -  `1.5 Version Changes <#Version_Changes>`__

         .. rubric:: assert() Function
            :name: assert-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Halts execution and prints a custom error message if a
            condition is ``false``\ (``0``). Note that the error message
            will be displayed in chat even if the command itself is in a
            ``[H: ]`` block.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     assert(condition, message)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     assert(condition, message, prefix)

         **Parameters**

         -  ``condition`` - The test condition that must evaluate to
            ``true``\ (``1``) for the macro to continue.
         -  ``message`` - The custom error message that is presented if
            the macro is halted due to the ``false``\ (``0``) condition.
         -  ``prefix`` - Determines if the error message should have the
            message prefix ``"Macro defined error: "``. Defaults to
            ``true``\ (``1``), set to ``false``\ (``0``) if you do not
            wish your custom error message to have the message prefix.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Checks to see if a player is a GM, and if they are not halts
            execution of the macro and displays output.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: assert(isGM(),"This macro is for GM use only.",0)]

            Chat output (if player is not GM):
            ``This macro is for GM use only.``

            | 
            | Halts execution of the macro if ``var`` is a number. This
              is useful for making sure the variables you work with are
              the variable type you expect.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: assert(! isNumber(var), "The variable is a number.",1)]

            Chat output (if ``var`` is a number):
            ``Macro defined error: The variable is a number.``

            Bear in mind, ``isNumber(var)`` returns ``true``\ (``1``)
            when var is a number, but assert continues when condition is
            ``true``\ (``1``). Using ``! isNumber(var)`` inverts the
            boolean value.

            .. rubric:: Usage Notes
               :name: usage-notes

            When aborting a macro called from another macro (for
            example, a library token), all macros are aborted, not just
            the one executing.

            Since 1.5.0 you can change that behaviour by using
            macro.catchAssert.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isGM() <isGM>`__
            `isNumber() <isNumber>`__
            `abort() <abort>`__

            `macro.catchAssert <macro.catchAssert>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``prefix`` parameter option.
            -  **1.5.0** - catch an assert with macro.catchAssert

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=assert&oldid=7274"

