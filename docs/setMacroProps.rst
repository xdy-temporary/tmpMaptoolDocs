==========================
setMacroProps - MapToolDoc
==========================

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

   .. rubric:: setMacroProps
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
            | ** This article needs:** *Examples using the new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setMacroProps()
               Function <#setMacroProps.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setMacroProps() Function
            :name: setmacroprops-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the properties for the specified `Macro
            Button <Token:Macro_Button>`__ on the `Current
            Token <Current_Token>`__ . The properties are
            passed to this function as a `String Property
            List <String_Property_List>`__. This function
            accepts either a `Macro Button
            Index </maptool/index.php?title=Token:Macro_Button_Index&action=edit&redlink=1>`__
            or the label of a `Macro
            Button <Token:Macro_Button>`__. If it is a
            label then all of `Macro
            Buttons <Token:Macro_Button>`__ on the
            `Current Token <Current_Token>`__ with a
            matching label are changed.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props, delim, id)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props, delim, id)

         **Parameters**

         -  ``index`` - The index of the macro button.
         -  ``label`` - The label of the macro button.
         -  ``props`` - A `String Property
            List <String_Property_List>`__ or `JSON
            Object <JSON_Object>`__ containing the
            properties for the button.

            -  ``applyToSelected`` - Should the macro be applied to the
               selected tokens.
            -  ``autoExecute`` - If the macro will be automatically
               executed when the button is clicked, accepts
               ``true``\ (``1``) or ``false``\ (``0``).
            -  ``color`` - The name of the color for the button.
            -  ``command`` - The command for the macro (only when using
               JSON version of function).
            -  ``fontColor`` - The name of the font color for the
               button.
            -  ``fontSize`` - The size of the font for the button.
            -  ``includeLabel`` - If the label will be output when the
               button is clicked. Accepts ``true``\ (``1``) or
               ``false``\ (``0``).
            -  ``group`` - The name of the group that the button belongs
               to.
            -  ``sortBy`` - The sort by value of the macro button.
            -  ``label`` - The label for the button.
            -  ``maxWidth`` - The maximum width of the button.
            -  ``minWidth`` - The minimum width of the button.
            -  ``playerEditable`` - Is the button player editable,
               accepts ``true``\ (``1``) or ``false``\ (``0``).
            -  ``tooltip`` - The tool tip for the macro button.
            -  ``compare`` - Takes a `JSON
               Array <JSON_Array>`__ which can contain one
               or more of the following keywords (only usable with JSON
               version of the function).

               -  ``applyToSelected`` - Use the macro applyToSelected
                  for common macro comparisons.
               -  ``autoExecute`` - Use the macro autoExec for common
                  macro comparisons.
               -  ``command`` - Use the macro command for common macro
                  comparisons.
               -  ``group`` - Use the macro group for common macro
                  comparisons.
               -  ``includeLabel`` - Use the macro includeLabel for
                  common macro comparisons.
               -  ``sortPrefix`` - Use the macro sortPrefix for common
                  macro comparisons.

         -  ``delim`` - The delimiter used in the `String Property
            List <String_Property_List>`__ that is sent to
            the ``props`` parameter, defaults to ``";"`` and can be
            omitted if you are sending a `JSON
            Object <JSON_Object>`__ to the ``props``
            parameter. If you are sending a `JSON
            Object <JSON_Object>`__ to the ``props``
            parameter, and using the ``id`` parameter, you can set this
            to ``"json"``.
         -  ``id`` - The token ``id`` of the token that the macro button
            is located on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setMacroProps(1, "color=red;fontColor=white")]

                  #. .. code-block:: none

                        [h: setMacroProps("Attack", "color=red;fontColor=white")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ability for ``props`` to accept a JSON
               object.
            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.3b53** - Added ability for ``command``, ``compare``,
               ``playerEditable``, ``applyToSelected``, ``autoExecute``,
               ``group``, and ``tooltip`` parameters.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setMacroProps&oldid=3729"

