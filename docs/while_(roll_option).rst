================================
while (roll option) - MapToolDoc
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

   .. rubric:: while (roll option)
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

            -  `1 WHILE Option <#WHILE_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Example <#Example_2>`__

         .. rubric:: WHILE Option
            :name: while-option

         **Introduced**: Version 1.3.b46

         | Repeatedly executes a statement until a condition becomes
           false.
         | The default **separator** is ``","``. Some examples of other
           useful separators: *nothing* ``""``, *space* ``" "`` and
           *break* ``"<br>"``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [WHILE(condition): body]

               #. .. code-block:: none

                     [WHILE(condition, separator): body]

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:num = 10]

               #. .. code-block:: none

                     [WHILE(num >= 0): num = num - 1]

         Outputs *9,8,7,6,5,4,3,2,1*

         .. rubric:: Example
            :name: example-1

         This example demonstrates how to put multiple instructions
         inside a ``while`` loop using the
         `[code():] <code_(roll_option)>`__ block
         extension.

         Note the use of the second parameter to ``while`` to force a
         line break in the HTML output. Also notice that putting text on
         separate lines does NOT force the output on separate lines; the
         HTML ``<br>`` element is needed for that.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: End = 5]

               #. .. code-block:: none

                     [H: Num = 0]

               #. .. code-block:: none

                     [WHILE(Num < End, "<br>"), CODE: {

               #. .. code-block:: none

                         Number is [Num = Num + 1],

               #. .. code:: de2

                         Next will be [Num+1]

               #. .. code-block:: none

                     }]

         Outputs:

         ``Number is 1, Next will be 2 Number is 2, Next will be 3 Number is 3, Next will be 4 Number is 4, Next will be 5 Number is 5, Next will be 6``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=while_(roll_option)&oldid=6008"

