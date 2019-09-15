=======================
macro.args - MapToolDoc
=======================

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

   .. rubric:: macro.args
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

         The variable *macro.args* holds the value of the argument
         passed to a trusted macro via the
         `MACRO() <macro_(roll_option)>`__ roll option.
         *macro.args* exists only within the macro that is called, and
         may be manipulated like any variable in a macro.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 1: Single parameter <#1:_Single_parameter>`__

                  -  `1.1.1 Calling Macro <#Calling_Macro>`__
                  -  `1.1.2 Called Macro <#Called_Macro>`__

               -  `1.2 2A: Multiple parameters using String Property
                  List <#2A:_Multiple_parameters_using_String_Property_List>`__

                  -  `1.2.1 Calling Macro <#Calling_Macro_2>`__
                  -  `1.2.2 Called Macro <#Called_Macro_2>`__

               -  `1.3 2B: Multiple parameters using JSON
                  Array <#2B:_Multiple_parameters_using_JSON_Array>`__

                  -  `1.3.1 Calling Macro using JSON
                     Array <#Calling_Macro_using_JSON_Array>`__
                  -  `1.3.2 Called Macro using JSON
                     Array <#Called_Macro_using_JSON_Array>`__

               -  `1.4 2C: Multiple parameters using JSON
                  Object <#2C:_Multiple_parameters_using_JSON_Object>`__

                  -  `1.4.1 Calling Macro using JSON
                     Object <#Calling_Macro_using_JSON_Object>`__
                  -  `1.4.2 Called Macro using JSON
                     Object <#Called_Macro_using_JSON_Object>`__

            -  `2 See Also <#See_Also>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: 1: Single parameter
            :name: single-parameter

         When a macro on a `library
         token <Token:library_token>`__ is called by
         another macro, the calling macro may pass one argument to the
         called macro:

         .. rubric:: Calling Macro
            :name: calling-macro

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- Call the getDamage macro -->

               #. .. code-block:: none

                     [h:damageDice="2d6"]

               #. .. code-block:: none

                     [MACRO("getDamage@Lib:test"): damageDice]

         .. rubric:: Called Macro
            :name: called-macro

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- getDamage Macro -->

               #. .. code-block:: none

                     [h:damageRoll = eval(macro.args) + 9]

               #. .. code-block:: none

                     You hit your target for [r:damageRoll] damage!

         In the example above, *damageDice* is the argument being passed
         to the macro **getDamage**, which resides on the **Lib:test**
         `library token <Token:library_token>`__. Within
         the **getDamage** macro, the variable ``macro.args`` is
         automatically generated and assigned the value of *damageDice*.

         It's important to note that only a single parameter can be
         passed to a macro and that parameter appears in the
         ``macro.args`` variable. If more than a single parameter needs
         to be sent to a macro, you may use string property lists, a
         JSON array or object, or a ``user-defined function``. The first
         two techniques are demonstrated below.

         .. rubric:: 2A: Multiple parameters using String Property List
            :name: a-multiple-parameters-using-string-property-list

         A string property list essentially bundles multiple values into
         a single string which would then be split back apart inside the
         macro body.

         .. rubric:: Calling Macro
            :name: calling-macro-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- Call the doDamage macro -->

               #. .. code-block:: none

                     [h:damageDice="2d6"]

               #. .. code-block:: none

                     [h:theToken = "Bobo Fett"]

               #. .. code-block:: none

                     [MACRO("getDamage@Lib:test"): "Damage="+damageDice+"; Token="+theToken]

         .. rubric:: Called Macro
            :name: called-macro-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- doDamage Macro -->

               #. .. code-block:: none

                     [h:dmg   = getStrProp(macro.args, "Damage")]

               #. .. code-block:: none

                     [h:tokid = getStrProp(macro.args, "Token")]

               #. .. code-block:: none

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: 2B: Multiple parameters using JSON Array
            :name: b-multiple-parameters-using-json-array

         The second way to pass multiple parameters is to use a `JSON
         Array <JSON_Array>`__ or `JSON
         Object <JSON_Object>`__.

         Using a JSON data type passes multiple values as a single unit.
         When using JSON data types, there will be a single parameter
         coming into the macro but because it's either an array or an
         object you can retrieve individual fields quite easily.

         As the `json.append() <json.append>`__ is being
         passed ``"[]"`` as the first parameter in this next code block,
         it's creating an empty `JSON
         Array <JSON_Array>`__ and then appending two new
         values to it.

         .. rubric:: Calling Macro using JSON Array
            :name: calling-macro-using-json-array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- Call the doDamage macro -->

               #. .. code-block:: none

                     [h:damageDice="2d6"]

               #. .. code-block:: none

                     [h:theToken = "Bobo Fett"]

               #. .. code-block:: none

                     [h:jsonData = json.append("[]", damageDice, theToken)]

               #. .. code:: de2

                     [MACRO("getDamage@Lib:test"): jsonData]

         .. rubric:: Called Macro using JSON Array
            :name: called-macro-using-json-array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- doDamage Macro -->

               #. .. code-block:: none

                     [h:dmg   = json.get(macro.args, 0)]

               #. .. code-block:: none

                     [h:tokid = json.get(macro.args, 1)]

               #. .. code-block:: none

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: 2C: Multiple parameters using JSON Object
            :name: c-multiple-parameters-using-json-object

         Notice that in this next example, the
         `json.set() <json.set>`__ is being passed
         ``"{}"`` as the first parameter. This indicates to the function
         that we want a `JSON Object <JSON_Object>`__.

         .. rubric:: Calling Macro using JSON Object
            :name: calling-macro-using-json-object

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- Call the doDamage macro -->

               #. .. code-block:: none

                     [h:damageDice="2d6"]

               #. .. code-block:: none

                     [h:theToken = "Bobo Fett"]

               #. .. code-block:: none

                     [h:jsonData = json.set("{}", "Damage", damageDice, "Token", theToken)]

               #. .. code:: de2

                     [MACRO("getDamage@Lib:test"): jsonData]

         .. rubric:: Called Macro using JSON Object
            :name: called-macro-using-json-object

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- doDamage Macro -->

               #. .. code-block:: none

                     [h:dmg   = json.get(macro.args, "Damage")]

               #. .. code-block:: none

                     [h:tokid = json.get(macro.args, "Token")]

               #. .. code-block:: none

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: See Also
            :name: see-also

         `macro.return <macro.return>`__,
         `[macro():] <macro_(roll_option)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macro.args&oldid=4040"

