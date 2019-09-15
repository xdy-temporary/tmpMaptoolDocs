============================
Roll Initiative - MapToolDoc
============================

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

   .. rubric:: Roll Initiative
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

         .. rubric:: Roll Initiative
            :name: roll-initiative

         This is a rather complex macro that will roll initiative for a
         group of tokens selected using a popular game system's rules.
         Specifically, the rules are:

         -  each token rolls 1d20 and adds a bonus (stored in the
            Initiative Property).
         -  ties go to the token with the higher bonus.
         -  groups of monsters all use the same roll -- or as
            implemented, tokens with the same image share the same roll.

         The code for this is below:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: initList = "booga=-1"];

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h, foreach(Selected, getSelected("json")), CODE:

               #. .. code-block:: none

                     {

               #. .. code:: de2

                        [switchToken(Selected)]

               #. .. code-block:: none

                      [SelectedGMName = getTokenImage()]

               #. .. code-block:: none

                        [arr = json.fromStrProp(initList)]

               #. .. code-block:: none

                        [if(json.contains(arr, SelectedGMName) != 0), CODE:

               #. .. code-block:: none

                        {

               #. .. code:: de2

                             [init = json.get(arr, SelectedGMName)]

               #. .. code-block:: none

                      };

               #. .. code-block:: none

                       {

               #. .. code-block:: none

                           [result = 1d20]

               #. .. code-block:: none

                             [init = result + getProperty("Initiative", Selected)]

               #. .. code:: de2

                             [tie = getProperty("Initiative", Selected) / 100]

               #. .. code-block:: none

                            [init = init + tie]

               #. .. code-block:: none

                          [initList = concat(initList, ";", SelectedGMName, "=", init)]

               #. .. code-block:: none

                       }]

               #. .. code-block:: none

                      

               #. .. code:: de2

                        [switchToken(Selected)]

               #. .. code-block:: none

                        [addToInitiative()]

               #. .. code-block:: none

                        [setInitiative(init)]

               #. .. code-block:: none

                     }]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     [h: sortInitiative()]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h,foreach(Selected, getSelected("json")), CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         [switchToken(Selected)]

               #. .. code:: de2

                      [init = getInitiative()]

               #. .. code-block:: none

                      [init = floor(init)]

               #. .. code-block:: none

                      [setInitiative(init)]

               #. .. code-block:: none

                     }]

         The result is that if you have a party of 4 PCs all with
         different token images, and a group of 4 skeletons with the
         same token image, and 2 zombies with the same token image,
         which would be typical, and you select all the tokens and run
         this macro, your initiative list will be populated with all the
         tokens. The 4 skeletons will all have the same initiative
         result. The 2 zombies will both have the same initiative
         result. If there are any ties, tokens with the higher
         initiative bonus will be presented first.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Roll_Initiative&oldid=5815"

