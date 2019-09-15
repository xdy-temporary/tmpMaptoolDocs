.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{RollOption
   |name=if
   |version=1.3b46
   |description=
   Branches the flow of the roll as determined by the condition.

   |usage=
   <source lang="mtmacro" line>
   [if(condition): true_body]
   </source>
   <source lang="mtmacro" line>
   [if(condition): true_body; false_body]
   </source>
   '''Parameters'''
   {{param|condition|The condition/s to check to determine which roll ({{code|true_body}} or {{code|false_body}}) is executed, if any. The condition/s can only contain one level of nested parenthesis.}}
   {{param|true_body|The roll that is executed if the {{code|condition}} evaluates to {{true}}. To use complex rolls in the {{code|true_body}}, you must use the {{roll|code}} roll option in conjunction with this roll option.}}
   {{param|false_body|The roll that is executed if the {{code|condition}} evaluates to {{false}}. If no {{code|false_body}} is given, there is no output if the {{code|condition}} evaluates to {{false}}. To use complex rolls in the {{code|false_body}}, you must use the {{roll|code}} roll option in conjunction with this roll option.}}
   '''Operators'''<br>
   Operators are used to compare two variables, strings, literal numbers, expressions, or function outputs within a {{code|condition}}.<br>

   ''Conditional Operators:''
   * {{code|>}} - Greater than
   * {{code|<}} - Less than
   * {{code|>{{=}}}}

- Greater than or equal to

-  

   .. raw:: mediawiki

      {{code|<{{=}}

   }} - Less than or equal to

-  

   .. raw:: mediawiki

      {{code|{{=}}

   {{=}}}} - Equal to

-  

   .. raw:: mediawiki

      {{code|!{{=}}

   }} or - Not equal

*Logical Operators:*

-  

   .. raw:: mediawiki

      {{code|&&}}

   - And

-  

   .. raw:: mediawiki

      {{code|{{!}}

   {{!}}}} - Or

*Boolean Operators:*

-  

   .. raw:: mediawiki

      {{code|true}}

-  

   .. raw:: mediawiki

      {{code|false}}

-  

   .. raw:: mediawiki

      {{code|!}}

   - Not

It is important to note that the *Equal to* condition operator must be
two equal signs ({{=}}}}). If you are checking for a text string, place
quotes around the text.

.. _known_problems:

-- Known Problems
=================

-  **Number of () levels**

The doesn't allow more than one level of . So,

.. code:: mtmacro
   :number-lines:

   [R, if(((1))): "true";"false"]

| will give an error.

-  **Help! There are ' ' in the output**

Note that currently

.. code:: mtmacro

   [r,if(val == something),CODE:{Print something}]

will produce extraneous single quotes in the output when the condition
is false. The workaround for this is to add an empty block for the false
side:

.. code:: mtmacro

   [r,if(val == something),CODE:{Print something};{}]

\|example= Sets the variable to if the variable equals .

.. code:: mtmacro
   :number-lines:

   [h:val=12]
   [h,if(val == 12): newVal=12*12]
   New Value = [r: newVal]

Returns 144}}

Example with logical operators:

.. code:: mtmacro
   :number-lines:

   [h,if((val > 12 && val < 24) || val == 5): val=1 ; val=0]

These examples perform the same function. If is not a number, make equal
.

.. code:: mtmacro
   :number-lines:

   [h, if (! isNumber(val)): val = 0)]

.. code:: mtmacro
   :number-lines:

   [h, if (isNumber(val) == 0): val = 0)]

.. code:: mtmacro
   :number-lines:

   [h, if (isNumber(val) == false): val = 0)]

The following will generate an error:

.. code:: mtmacro
   :number-lines:

   [h,if(getName(getSelected()) == "Giant Rat"): val=1]  --- ERROR, too many parenthesis on condition!
   [h,if(getName() == "Giant Rat")): val=1] ---  This is OK.

\|also= , , , `Introduction to Macro
Branching <Introduction_to_Macro_Branching>`__ }}

`Category:Branching Roll Option <Category:Branching_Roll_Option>`__
