==============================
for (roll option) - MapToolDoc
==============================

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

   .. rubric:: for (roll option)
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

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 [for():] Roll
               Option <#.5Bfor.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: [for():] Roll Option
            :name: for-roll-option

         .. container::

            \* **Introduced in version 1.3.b46**

         Executes a statement for a number of iterations based on a
         start and end value.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(var, start, end): body]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(var, start, end, stepsize): body]

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(var, start, end, stepsize, separator): body]

         | **Parameters**
         | The ``var`` variable counts from ``start`` towards ``end``
           during the loop, and the optional ``stepsize`` (default
           ``+1``) is added to ``var`` at each iteration. Note that in
           the standard incrementing usage with a ``stepsize`` of ``1``,
           the ``body`` does not execute when ``var`` reaches ``end``.
         | Note that ``stepsize`` must be integer and not 0. Floating
           values will be rounded down.
         | ``list_separator`` default value is ``","``. Some examples of
           other useful separators: *nothing* ``""``, *space* ``" "``
           and *break* ``"<br>"``.

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(i,0,10): "i is now " + i]

         Counts up from 0 to 9.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [for(i,10,0,-2): "i is now " + i]

         Counts down even numbers from 10 to 0.

         .. rubric:: See Also
            :name: see-also

         `[foreach():] </rptools/wiki/foreach_(roll_option)>`__,
         `Introduction to Macro
         Loops </rptools/wiki/Introduction_to_Macro_Loops>`__

         .. rubric:: Version Changes
            :name: version-changes

         -  **1.3b54** - Changed the comparison operator when comparing
            the ``var`` to ``end`` when determining whether to continue
            executing a new iteration. In version 1.3b53 and earlier, on
            each iteration it compared if ``var`` was less than or equal
            to ``end``. As of version 1.3b54, it is now comparing if
            ``var`` is less than ``end``.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=for_(roll_option)&oldid=6006"

