================================
macro (roll option) - MapToolDoc
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

   .. rubric:: macro (roll option)
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

            -  `1 [macro():] Roll
               Option <#.5Bmacro.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: [macro():] Roll Option
            :name: macro-roll-option

         .. container::

            \* **Introduced in version 1.3b46**

         Runs the named macro, returning its output in the form of the
         `macro.return <macro.return>`__ special variable.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [macro("macro_name@location"): macro_arguments]

         **Parameters**

         -  ``macro_name`` - The name of the macro button that is run.
         -  ``location`` - The location of the macro button that is run.
         -  ``macro_arguments`` - Sent to the called macro in the form
            of the `macro.args <macro.args>`__ special
            variable.

         **Location Requirements**

         The ``location`` can be one of the following:

         -  ``TOKEN`` - The currently impersonated token (use the word
            ``TOKEN``, not the token's name).
         -  ``campaign``
         -  ``global``
         -  ``Lib:*`` Library Token - A `Library
            Token <Library_Token>`__ in the current
            campaign.
         -  ``this`` - If the macro is calling another macro on the same
            `Library Token <Library_Token>`__, ``this``
            may be used instead of retyping the full `Library
            Token <Library_Token>`__ name.

         **Notes**

         When a token macro calls another macro, the macro instructions
         in the *called* macro are executed against the *calling* token
         (in other words, the macro uses properties available on the
         calling token and applies all results to that token), unless
         the focus is explicitly changed to another token via either a
         roll option, or the
         `switchToken() <switchToken>`__ function, or the
         `getLibProperty() <getLibProperty>`__ function
         within the *called* macro. This applies even if the `Current
         Token <Current_Token>`__ was explicitly changed
         prior to using the **[macro():]** roll option.

         Also- as of at least 1.3.b50- a variable must be given for
         ``macro_arguments``, or the *"Could not execute the command:
         Undefined function: MACRO"* error will result. However, the
         variable given as ``macro_arguments`` doesn't have to be used,
         and can be set to an empty string (``""``).

         This roll option may not interact with other roll options the
         way you expect. For example:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(Condition),MACRO("getDamage@Lib:combat"): damageRoll]

         ``getDamage`` gets executed regardless of the value of
         ``Condition``. However, if ``Condition`` is not true, the
         arguments to the macro will be empty instead of containing
         ``damageRoll``. You probably want:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [if(Condition): evalMacro('[MACRO("getDamage@Lib:combat"): damageRoll]')]

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [MACRO("getDamage@Lib:combat"): damageRoll]

         Calls the macro ``getDamage`` which resides on a `Library
         Token <Library_Token>`__ called ``Lib:combat``,
         and passes the variable ``damageRoll`` as an argument to the
         called macro.

         **Passing multiple arguments to a called macro**

         Note that only one variable can be passed to the called macro.
         To pass multiple values, you must "package" them into a format
         that can be stored in a single variable to be passed to the
         called macro, and then unpackaged appropriately to recover
         local variables used in the called macro. `JSON
         Objects <JSON_Object>`__ and `JSON
         Arrays <JSON_Array>`__ work very well for this
         purpose (although string lists and StrProps can also serve this
         purpose, they have more limitations and are less recommended).
         For example, multiple values can be stored into a json array,
         which becomes the argument passed in the macro call:

         **Using a**\ `JSON Array <JSON_Array>`__\ **to
         pass multiple values (order matters, names do not)**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ variable1 = "hello" ]

               #. .. code-block:: none

                     [ variable2 = "world" ]

               #. .. code-block:: none

                     [ passedVars = json.append( "", variable1, variable2 )] <!-- package up variables into a json array to be passed to called macro -->

               #. .. code-block:: none

                     [MACRO("calledMacro@this"): passedVars ] <!-- macro call, with values being passed -->

               #. .. code:: de2

                     [ resultVar = macro.return ]  <!-- this is what you get back from the called macro -->

         Within the "called macro", the
         `macro.args <macro.args>`__ (macro arguments)
         must be unpackaged to recover the values stored in the array:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ var1 = json.get( macro.args, 0 )]

               #. .. code-block:: none

                     [ var2 = json.get( macro.args, 1 )]

               #. .. code-block:: none

                     <!-- do stuff with your new variables -->

               #. .. code-block:: none

                     [ macro.return = var1 +" "+ var2 ] <!-- this is what you can send back to the calling macro (can also be another JSON Object or array -->

         Note that using a `JSON Array <JSON_Array>`__ to
         pass & unpack values, rather than a `JSON
         Object <JSON_Object>`__, has the added advantage
         that if the called macro is also a `user defined
         function </maptool/index.php?title=user_defined_function&action=edit&redlink=1>`__
         (see `defineFunction <defineFunction>`__), the
         exact same commands given in the example above can be used to
         separate individual arguments passed in the calling "function",
         since function arguments are automatically bundled into a `JSON
         Array <JSON_Array>`__ and passed to the
         `macro.args <macro.args>`__ special variable.

         **Using a**\ `JSON Object <JSON_Object>`__\ **to
         pass multiple values (names matter, order does not)**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ variable1 = "hello" ]

               #. .. code-block:: none

                     [ variable2 = "world" ]

               #. .. code-block:: none

                     [ passedVars = json.set( "{}", "variable2", variable2, "variable1", variable1 )] <!-- package up variables into a json array to be passed to called macro.  Note that the order here does not matter, but the labels in quotes are needed to be able to retrieve the correct values in the called macro -->

               #. .. code-block:: none

                     [MACRO("calledMacro@this"): passedVars ] <!-- macro call, with values being passed -->

               #. .. code:: de2

                     [ resultVar = macro.return ]  <!-- this is what you get back from the called macro -->

         Within the "called macro", the
         `macro.args <macro.args>`__ (macro arguments)
         must be unpackaged to recover the values stored in the array:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ var1 = json.get( macro.args, "variable1" )]<!-- actually the second label / value pair in the object --> 

               #. .. code-block:: none

                     [ var2 = json.get( macro.args, "variable2" )]<!-- the order does not matter, but the label must be accurate to retrieve the correct value -->

               #. .. code-block:: none

                     <!-- do stuff with your new variables -->

               #. .. code-block:: none

                     [ macro.return = var1 +" "+ var2 ] <!-- this is what you can send back to the calling macro (can also be another JSON Object or array -->

         .. rubric:: See Also
            :name: see-also

         `macro.args <macro.args>`__,
         `macro.return <macro.return>`__,
         `defineFunction <defineFunction>`__, `More
         Branching Options <More_Branching_Options>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macro_(roll_option)&oldid=6297"

