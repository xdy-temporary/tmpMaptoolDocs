============================
addToInitiative - MapToolDoc
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

   .. rubric:: addToInitiative
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

            -  `1 addToInitiative()
               Function <#addToInitiative.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: addToInitiative() Function
            :name: addtoinitiative-function

         .. container:: template_description

            Adds the `Current Token <Current_Token>`__ to
            the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function will not assign any initiative value to the
            `tokens <Token:token>`__, you can use the
            `setInitiative() <setInitiative>`__ function

            to set the initiative value of tokens.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: addToInitiative()]

               #. .. code-block:: none

                     [H: return = addToInitiative( AllowDuplicates, value ) ]

         **Parameters**

         -  ``AllowDuplicates`` - If false (default) then will not add
            the token if it is already in the initiative list. If true
            (1) an additional entry will be added to the initiative list
            (so there could be multiple initiative entries for the same
            token).
         -  ``value`` - The initiative value to set. If included, the
            initiative will be set even if the token is already on the
            initiative list and duplicates are not allowed.
         -  ``return`` - Returns 1 if added to the initiative, 0 if did
            not.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following example shows how to add a `Current
            Token <Current_Token>`__ to the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__,
            set
            its initiative and then sort the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            Normally you would not sort the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__
            every time you add a `Current
            Token <Current_Token>`__ but its done here to
            show you how it is done.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: addToInitiative()]

                  #. .. code-block:: none

                        [h: setInitiative(1d20)]

                  #. .. code-block:: none

                        [h: sortInitiative()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setInitiative() <setInitiative>`__
            `addAllPCsToInitiative() <addAllPCsToInitiative>`__
            `addAllToInitiative() <addAllToInitiative>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addToInitiative&oldid=4014"

