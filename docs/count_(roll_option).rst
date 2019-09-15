================================
count (roll option) - MapToolDoc
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

   .. rubric:: count (roll option)
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

         .. rubric:: COUNT Option
            :name: count-option

         **Introduced**: Version 1.3.b41

         The COUNT option executes a statement for a specified number of
         times, storing the number of the current iteration in a
         variable called
         `roll.count </rptools/wiki/Macros:Special_Variables:roll.count>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [COUNT(num): body]

               #. .. code-block:: none

                     [COUNT(num, separator): body]

         The `roll.count </rptools/wiki/roll.count>`__ variable will
         take on values from ``0`` to (``number of loops - 1``). The
         optional separator (default ``","``) is printed between each
         iteration. Some examples of other useful separators: *nothing*
         ``""``, *space* ``" "`` and *break* ``"<br>"``.

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:numHits=3]

               #. .. code-block:: none

                     [COUNT(numHits): Damage = Damage + 1d12]

         This will iterate the ``Damage = Damage + 1d12`` operation 3
         times, separating the result of each iteration with the default
         separator (a comma). An optional second argument to ``COUNT()``
         allows the setting of a different separator.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=count_(roll_option)&oldid=6355"

