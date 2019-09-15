========================
oldFunction - MapToolDoc
========================

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

   .. rubric:: oldFunction
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

            -  `1 oldFunction()
               Function <#oldFunction.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: oldFunction() Function
            :name: oldfunction-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            If a user-defined function redefines a standard MapTool
            function or another user-defined function -- for instance, a
            user defines a function called ``eval()``, redefining the
            standard MapTool `eval() <eval>`__ --
            **oldFunction()** can be used in the user-defined function
            to call the original function. When a user-defined function
            redefines an existing function, it keeps track of the
            function that it redefined. Due to this tracking, it is
            possible to redefine a function multiple times and
            **oldFunction()** will always reference the previous
            function in the chain. **Note:** Do not rely on a specific
            order in the function chain unless you are sure that the
            functions will be redefined in that order. Calls to
            `defineFunction() <defineFunction>`__ within
            `onCampaignLoad <onCampaignLoad>`__ macros on
            different `Library Tokens <Library_Token>`__
            are not executed in any standard order.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     oldFunction(SPECIAL)

         **Parameter**

         -  ``SPECIAL`` - oldFunction supports the same parameters as
            the function that it is referencing.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Within a user-defined function named ``eval()``,
            **oldFunction()** is used to call the standard MapTool
            `eval() <eval>`__ function.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h, if ( arg(0) == 0 ), code:
                     {
                         [h: macro.return = 0]
                     };{
                         [h: macro.return = oldFunction( arg(0) ) ]
                     }]

            By having access to the original function definition, this
            example is able to provide custom or standard return values
            when called.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() <defineFunction>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=oldFunction&oldid=3158"

