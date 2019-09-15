==================
table - MapToolDoc
==================

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

   .. rubric:: table
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

            -  `1 table() Function <#table.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: table() Function
            :name: table-function

         .. container:: template_version

            • **Introduced in version 1.3b39**

         .. container:: template_description

            Gets the text value from the specified ``table``. If the row
            is not specified then the default ``roll`` for the ``table``
            is used. The row can be either a constant or a ``roll``.
            Note that what this function returns is interpreted as
            either a string or a number. You can put code in a table
            entry but that too will be returned as a string and will not
            be evaluated. To evaluate the result you can use
            `eval() </rptools/wiki/eval>`__ to evaluate e.g. the table
            entry ``1d5`` and `evalMacro() </rptools/wiki/evalMacro>`__
            to evaluate e.g. the table entry ``[r:1d5]``

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     table(name)

               #. .. code-block:: none

                     table(name, row)

               #. .. code-block:: none

                     tbl(name)

               #. .. code-block:: none

                     tbl(name, row)

         **Parameters**

         -  ``name`` - A string containing the name of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
         -  ``row`` - The row of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            that should be returned.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:** Display a random value from table ``"tbl1"``
            using default roll:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: table("tbl1")]

            **Example 2:** Display the first value from table
            ``"tbl1"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: table("tbl1", 1)]

            **Example 3:** Display one of the first four values from
            ``"tbl1"``, chosen randomly:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: table("tbl1", "1d4")]

            **Example 4:** Display a table row that corresponds to a
            token property's value (the value must be numeric):

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: table("tbl1", Intelligence)]

                  #. .. code-block:: none

                        [r: table("tbl1", getProperty("PCLevel"))]

            **Example 5:** Evaluate the outcome of a table entry. The
            table entry **must** thus be something that can be
            evaluated, like ``1d10`` or ``roll(1,6)`` or ``3+5``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: eval(table("tbl1"))]

            **Example 5:** Evaluate the outcome of a table entry that
            contains code. The table entry **can** thus contain code,
            but its not required. 'code' in this case is anything
            between [brackets]. An example table entry could be
            *[h:roll=1d20]You [r:if(roll<10, 'hit', 'miss')] your
            target.* :

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: evalMacro(table("tbl1"))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `tableImage() </rptools/wiki/tableImage>`__ There is a tool
            available to import tables from excel. You can find more
            about this
            `here <http://forums.rptools.net/viewtopic.php?f=3&t=11568#p124557>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=table&oldid=6720"

