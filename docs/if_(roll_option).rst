=============================
if (roll option) - MapToolDoc
=============================

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

   .. rubric:: if (roll option)
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

            -  `1 [if():] Roll Option <#.5Bif.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__

                  -  `1.1.1 -- Known Problems <#--_Known_Problems>`__

               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: [if():] Roll Option
            :name: if-roll-option

         .. container::

            \* **Introduced in version 1.3b46**

         Branches the flow of the roll as determined by the condition.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(condition): true_body]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(condition): true_body; false_body]

         **Parameters**

         -  ``condition`` - The condition/s to check to determine which
            roll (``true_body`` or ``false_body``) is executed, if any.
            The condition/s can only contain one level of nested
            parenthesis.
         -  ``true_body`` - The roll that is executed if the
            ``condition`` evaluates to ``true``\ (``1``). To use complex
            rolls in the ``true_body``, you must use the
            `[code():] <code_(roll_option)>`__ roll option
            in conjunction with this roll option.
         -  ``false_body`` - The roll that is executed if the
            ``condition`` evaluates to ``false``\ (``0``). If no
            ``false_body`` is given, there is no output if the
            ``condition`` evaluates to ``false``\ (``0``). To use
            complex rolls in the ``false_body``, you must use the
            `[code():] <code_(roll_option)>`__ roll option
            in conjunction with this roll option.

         | **Operators**
         | Operators are used to compare two variables, strings, literal
           numbers, expressions, or function outputs within a
           ``condition``.

         *Conditional Operators:*

         -  ``>`` - Greater than
         -  ``<`` - Less than
         -  ``>=`` - Greater than or equal to
         -  ``<=`` - Less than or equal to
         -  ``==`` - Equal to
         -  ``!=`` or ``ne`` - Not equal

         *Logical Operators:*

         -  ``&&`` - And
         -  ``||`` - Or

         *Boolean Operators:*

         -  ``true``
         -  ``false``
         -  ``!`` - Not

         It is important to note that the *Equal to* condition operator
         must be two equal signs (``==``). If you are checking for a
         text string, place quotes around the text.

         .. rubric:: -- Known Problems
            :name: known-problems

         -  **Number of () levels**

         The ``[if():]`` doesn't allow more than one level of ``()``.
         So,

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [R, if(((1))): "true";"false"]

         | will give an error.

         -  **Help! There are ' ' in the output**

         Note that currently

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r,if(val == something),CODE:{Print something}]

         will produce extraneous single quotes in the output when the
         condition is false. The workaround for this is to add an empty
         block for the false side:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r,if(val == something),CODE:{Print something};{}]

         .. rubric:: Example
            :name: example

         Sets the variable ``newVal`` to ``12*12`` if the variable
         ``val`` equals ``12``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:val=12]

               #. .. code-block:: none

                     [h,if(val == 12): newVal=12*12]

               #. .. code-block:: none

                     New Value = [r: newVal]

         Returns ``New Value = 144``

         Example with logical operators:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,if((val > 12 && val < 24) || val == 5): val=1 ; val=0]

         These examples perform the same function. If ``val`` is not a
         number, make ``val`` equal ``0``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h, if (! isNumber(val)): val = 0)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h, if (isNumber(val) == 0): val = 0)]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h, if (isNumber(val) == false): val = 0)]

         The following will generate an error:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,if(getName(getSelected()) == "Giant Rat"): val=1]  --- ERROR, too many parenthesis on condition!

               #. .. code-block:: none

                     [h,if(getName() == "Giant Rat")): val=1] ---  This is OK.

         .. rubric:: See Also
            :name: see-also

         `if() <if>`__,
         `isNumber() <isNumber>`__,
         `[code():] <code_(roll_option)>`__, `Introduction
         to Macro
         Branching <Introduction_to_Macro_Branching>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=if_(roll_option)&oldid=6025"

