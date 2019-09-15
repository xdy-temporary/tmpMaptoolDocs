=========================
listContains - MapToolDoc
=========================

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

   .. rubric:: listContains
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

            -  `1 listContains()
               Function <#listContains.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: listContains() Function
            :name: listcontains-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the number of occurrences of a value in a `String
            List <String_List>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     listContains(list, value)

               #. .. code-block:: none

                     listContains(list, value, delim)

         **Parameters**

         -  ``list`` - The `String List <String_List>`__
            that is checked for occurrences of the ``value``.
         -  ``value`` - The value to search the `String
            List <String_List>`__ for occurrences.
         -  ``delim`` - The delimiter that separates the values in the
            `String List <String_List>`__; defaults to
            ``","``.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: listContains("a,b,c,a,b,a", "a")]

            Returns ``3``

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: MyStringList = "1#2#3#4#1#2#3#1#2"]

                  #. .. code-block:: none

                        [r: listContains(MyStringList, "3", "#")]

            Returns ``2``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `listFind() <listFind>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listContains&oldid=3389"

