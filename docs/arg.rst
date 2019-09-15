================
arg - MapToolDoc
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

   .. rubric:: arg
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

            -  `1 arg() Function <#arg.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: arg() Function
            :name: arg-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Is used to extract arguments that are passed to a macro when
            called as a user defined function.
            User functions are defined with the
            `defineFunction() </rptools/wiki/defineFunction>`__
            function. Once you have defined a function you can call it
            as you would call any of the existing functions, for example
            ``attackRoll(Strength, -1)``. The ``arg()`` function is used
            within the macro that is called to extract each of these
            arguments. The index of the first argument is 0.

            | 
            | The ```argCount()`` </rptools/wiki/argCount>`__ function
              is often used in conjunction with ``arg()`` to determine
              the number

            of arguments that have been passed to the user defined
            function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     arg(index)

         **Parameters**

         -  ``index`` - The index of the argument to return. Indexes
            begin at ``0``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Given a user defined function called ``attackRoll()`` which
            accepts two arguments, which are attribute value and
            bonus you could call it in the following way.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [attackRoll(12, -1)]

            Then inside the macro that implements the user defined
            function you can do the following.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: attr = arg(0)]

                  #. .. code-block:: none

                        [h: bonus = arg(1)]

                  #. .. code-block:: none

                        [r: 1d20 + floor(attr/2) + bonus]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() </rptools/wiki/defineFunction>`__,
            `isFunctionDefined() </rptools/wiki/isFunctionDefined>`__,
            `argCount() </rptools/wiki/argCount>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=arg&oldid=7190"

