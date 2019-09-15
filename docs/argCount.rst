=====================
argCount - MapToolDoc
=====================

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

   .. rubric:: argCount
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

            -  `1 argCount() Function <#argCount.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: argCount() Function
            :name: argcount-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Is used to determine the number of arguments that have been
            passed to a user defined function.
            User functions are defined with the ``defineFunction()``,
            once you have defined the function you can call it is you
            would call any of the existing functions. You can then use
            the ``argCount()`` function to determine how many arguments
            were passed when it was called.

            Once the number of arguments have been determined you can
            use ```arg()`` </rptools/wiki/arg>`__ to retrieve them.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     argCount()

         .. rubric:: Example
            :name: example

         .. container:: template_example

            An example of a simple macro that would be defined as a user
            defined function. This function will add together
            all of the arguments that are passed to it.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: numArgs = argCount()]

                  #. .. code-block:: none

                        [h: total = 0]

                  #. .. code-block:: none

                        [h,count(numArgs): total = total + arg(roll.count)]

                  #. .. code-block:: none

                        [r: total]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `defineFunction() </rptools/wiki/defineFunction>`__,
            `isFunctionDefined() </rptools/wiki/isFunctionDefined>`__,
            `arg() </rptools/wiki/arg>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=argCount&oldid=7191"

