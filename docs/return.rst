===================
return - MapToolDoc
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

   .. rubric:: return
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

            -  `1 return() Function <#return.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__

                  -  `1.2.1 Calling Macro <#Calling_Macro>`__
                  -  `1.2.2 Called Macro <#Called_Macro>`__
                  -  `1.2.3 Results <#Results>`__

               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: return() Function
            :name: return-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Is used to conditionally return from the execution of a
            macro like an abort, but not stopping further macro
            execution. Optionally also returning a value by
            automatically assigning
            `macro.return <macro.return>`__. If the first
            argument to ``return()`` is 0 then the return is happening.
            If the first argument to ``return()`` is non zero then the
            macro continues. The optional second argument of
            ``return()`` defines if there is a value that should be
            returned to a calling macro. Any other output is discarded
            when using ``return()``.
            Common uses for this function are

            -  Ending a macro with or without a return value to stop the
               further execution of the following lines in the current
               macro.
            -  The macro has conditions and based on these you want to
               return different values and not continue further in the
               current macro.

            If you prefer to display an error message when exiting the
            macro see the ```assert()`` <assert>`__
            function or if you want to abort the flow of overall macro
            execution (e.g. in case of an error) see the
            ```abort()`` <abort>`__ function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     return(continue, returnValue)

         **Parameters**

         -  ``continue`` - ``0`` if the return function should end the
            current macro, nonzero if it should not. So consistent to
            what the abort function is doing.
         -  ``returnValue`` - Optional. Any value passed in here will
            automatically be used as a return value (set to
            macro.return) and passed to the calling macro.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            The following example is about a called macro using the
            **return()** function to return a result to the calling
            macro. The calling macro could also be in a user defined
            function and then just used as a function in the caller
            macro.
            .. rubric:: Calling Macro
               :name: calling-macro

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Call the testReturn library macro -->

                  #. .. code-block:: none

                        [MACRO("testReturn@Lib:test"): ""]

                  #. .. code-block:: none

                        Response is [r:macro.return].

            .. rubric:: Called Macro
               :name: called-macro

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- testReturn macro in Lib:test token -->

                  #. .. code-block:: none

                        [h: return(0, "hello world")]

                  #. .. code-block:: none

                        [h: "this will not be executed anymore"]

                  #. .. code-block:: none

                        [h: macro.return = "this will not be set"]

            .. rubric:: Results
               :name: results

            TokenName: Response is hello world.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `assert() <assert>`__
            `abort() <abort>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.0** - introduced return function

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=return&oldid=7245"

