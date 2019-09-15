=======================
roll.count - MapToolDoc
=======================

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

   .. rubric:: roll.count
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

         The special variable *roll.count* holds the current iteration
         of current loop. It may be used with the following roll options
         for looping:

         -  `COUNT(): <Macros:Branching_and_Looping#COUNT_Option>`__
         -  `FOR(): <Macros:Branching_and_Looping#FOR_Option>`__
         -  `FOREACH(): <Macros:Branching_and_Looping#FOREACH_Option>`__
         -  `WHILE(): <Macros:Branching_and_Looping#WHILE_Option>`__

         The *roll.count* begins at 0.

         .. rubric:: Examples
            :name: examples

         **Simple Count**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [COUNT(5, "<br>"): "This is roll " + roll.count]

         *Outputs:*

         ::

            This is roll 0
            This is roll 1
            This is roll 2
            This is roll 3
            This is roll 4

         **Inner and Outer Loop**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r,foreach(item,"a,b,c,d,e,f",""),code: {

               #. .. code-block:: none

                       Loop: [r: roll.count] - [r: item] - 

               #. .. code-block:: none

                         [r,count(6): roll.count]<br>

               #. .. code-block:: none

                     }]

         *Outputs:*

         ::

             Loop: 0 - a - 0, 1, 2, 3, 4, 5 
             Loop: 1 - b - 0, 1, 2, 3, 4, 5 
             Loop: 2 - c - 0, 1, 2, 3, 4, 5 
             Loop: 3 - d - 0, 1, 2, 3, 4, 5 
             Loop: 4 - e - 0, 1, 2, 3, 4, 5 
             Loop: 5 - f - 0, 1, 2, 3, 4, 5 

         .. rubric:: Related Pages
            :name: related-pages

         -  `Branching and Looping
            Options <Macros:Branching_and_Looping>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=roll.count&oldid=7443"

