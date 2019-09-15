===============================
code (roll option) - MapToolDoc
===============================

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

   .. rubric:: code (roll option)
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

            -  `1 CODE <#CODE>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Nested CODE Blocks <#Nested_CODE_Blocks>`__

         .. rubric:: CODE
            :name: code

         **Introduced**: Version 1.3.b46

         The CODE option is used in conjunction with looping / branching
         options to execute multiple statements within a single "block"
         of a loop or branch, allowing the creation of more complex
         loops and branches.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [CODE: { code_block }]

         The *code_block* is a collection of text and macro code,
         enclosed in a single {} pair. Everything within the {} is
         treated as a single block for the purposes of any looping or
         branching options.

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:num=5]

               #. .. code-block:: none

                     [WHILE(num > 0), CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                       This is iteration [r:num] <br>

               #. .. code:: de2

                       There are [r:num-1] iterations left<br>

               #. .. code-block:: none

                       [num=num-1]

               #. .. code-block:: none

                     }]

         Outputs

         ::

            This is iteration 5 There are 4 iterations left
            4, This is iteration 4 There are 3 iterations left
            3, This is iteration 3 There are 2 iterations left
            2, This is iteration 2 There are 1 iterations left
            1, This is iteration 1 There are 0 iterations left
            0

         **NOTE**: the digit output at the beginning of each line is an
         artifact of the WHILE loop's evaluation of *num* - since this
         roll does not have the *h* option active, the result of that
         evaluation is displayed.

         .. rubric:: Nested CODE Blocks
            :name: nested-code-blocks

         To nest CODE:{} blocks, use a second CODE:{ } option, like so:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:d20roll=1d20]

               #. .. code-block:: none

                     [h:attackRoll=d20roll+AttackBonus]

               #. .. code-block:: none

                     [h,IF(attackRoll >= 16),CODE:

               #. .. code-block:: none

                     {

               #. .. code:: de2

                       [IF(d20roll == 20),CODE:

               #. .. code-block:: none

                       {

               #. .. code-block:: none

                         The attack is a critical hit!

               #. .. code-block:: none

                         [h:damage=critDamage]

               #. .. code-block:: none

                       };

               #. .. code:: de2

                       {

               #. .. code-block:: none

                         The attack is a hit!

               #. .. code-block:: none

                         [h:damage=regDamage]

               #. .. code-block:: none

                       };]

               #. .. code-block:: none

                     };

               #. .. code:: de2

                     {

               #. .. code-block:: none

                       The attack misses!

               #. .. code-block:: none

                     };]

         MapTool can only handle two levels of nested code.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=code_(roll_option)&oldid=2952"

