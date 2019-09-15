================
set - MapToolDoc
================

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

   .. rubric:: set
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

         .. rubric:: set() Function
            :name: set-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the value of a variable.
            This function is rarely used because a simple assignment to
            a variable name can be used instead. However, using this
            function allows the first parameter to be a variable that
            identifies the variable name to be assigned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: set(varName, val)]

         **Parameters**

         -  ``varName`` - Variable name or a string containing a valid
            variable name.
         -  ``val`` - The value to set the variable to.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            A simple use:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: set("test", 33)]

                  #. .. code-block:: none

                        [r: test]

            Returns

            ::

                  33

            A more sophisticated example that shows passing a string
            expression as the first parameter:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: var1="te"]

                  #. .. code-block:: none

                        [h: var2="st"]

                  #. .. code-block:: none

                        [h: set(var1+var2, 33)]

                  #. .. code-block:: none

                        [r: test]

            Returns

            ::

                  33

            Both of the above examples are equivalent to:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: test = 33]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=set&oldid=7439"

