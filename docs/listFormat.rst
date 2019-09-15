=======================
listFormat - MapToolDoc
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

   .. rubric:: listFormat
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

         .. rubric:: listFormat() Function
            :name: listformat-function

         .. container:: template_description

            Returns a custom-formatted version of the list.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ listFormat(list, listFormat, itemFormat, separator) ]

               #. .. code-block:: none

                     [ listFormat(list, listFormat, itemFormat, separator, delim) ]

         -  listFormat is a string that is emitted once. It should
            contain the text "%list", which is replaced with the
            formatted items.
         -  itemFormat is emitted once per item. Each instance of
            "%item" in the string is replaced with the value of the list
            item.
         -  separator is emitted in between the formatted items.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [ listFormat("apple,bear,cat", "BEGIN LIST<br>%list<br>END LIST", "This item is: %item", "<br>") ]

            (prints items on separate lines)

            Convert a string list to html list:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [R: listFormat( "apple, bear, cat", "<ul>%list</ul>", "<li>%item</li>", "" ) ]

            Produces:

            -  apple
            -  bear
            -  cat

            | 
            | Create an option list input (drop-down list selection) for
              an html form, with the names of selected tokens:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [R: listFormat( getSelectedNames( "%%" ), 

                  #. .. code-block:: none

                            "<select name='test'>%list</select>", 

                  #. .. code-block:: none

                            "<option value='%item'>%item</option>", 

                  #. .. code-block:: none

                            "",  

                  #. .. code:: de2

                            "%%" ) 

                  #. .. code-block:: none

                        ]

            The first argument is the list, returned by
            `getSelectedNames() <getSelectedNames>`__: it
            has a delimiter specified ("%%"), to avoid PC names with
            commas or anything other than "%%" from appearing as more
            than one item. The second argument specifies html (text) to
            go around the entire formatted *list*, and the third is html
            to wrap around each *item* in the list. The fourth argument
            is blank (empty), since no separator between items is needed
            in this case. The fifth argument is usually optional, but in
            this case is the same delimiter specified in
            getSelectedNames(), to allow listFormat to find each item in
            the list.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=listFormat&oldid=4155"

