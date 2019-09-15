==========================
addTableEntry - MapToolDoc
==========================

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

   .. rubric:: addTableEntry
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

            -  `1 addTableEntry()
               Function <#addTableEntry.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: addTableEntry() Function
            :name: addtableentry-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Adds a new row to the specified table. **Note:** adding a
            row to a table will not automatically change the table row
            value, so this should be updated to avoid possible errors
            (See `setTableRoll() </rptools/wiki/setTableRoll>`__
            function).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     addTableEntry(tableName,rangeStart,rangeEnd,result)

               #. .. code-block:: none

                     addTableEntry(tableName,rangeStart,rangeEnd,result,imageId)

         **Parameters**

         -  ``tableName`` - A string containing the name of the Table.
         -  ``rangeStart`` - An integer indicating the lowest value that
            will return this row.
         -  ``rangeEnd`` - An integer indicating the highest value that
            will return this row.
         -  ``result`` - A string containing the result returned by the
            **table()** function.
         -  ``imageId`` - Optional and is the asset id of an image that
            will be returned by the **tableImage()** function.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:addTableEntry("test",1,3,"bert")]

                  #. .. code-block:: none

                        [r:addTableEntry("test",4,4,"fred")]

                  #. .. code-block:: none

                        [r:addTableEntry("test",5,5,"alf", getTokenImage())]

                  #. .. code-block:: none

                        [r:setTableRoll("test","")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setTableRoll() </rptools/wiki/setTableRoll>`__
            `table() </rptools/wiki/table>`__
            `tableImage() </rptools/wiki/tableImage>`__
            `deleteTableEntry() </rptools/wiki/deleteTableEntry>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addTableEntry&oldid=6727"

