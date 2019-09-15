=============================
deleteTableEntry - MapToolDoc
=============================

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

   .. rubric:: deleteTableEntry
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

            -  `1 deleteTableEntry()
               Function <#deleteTableEntry.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: deleteTableEntry() Function
            :name: deletetableentry-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Removes a row from the specified table. **Note:** deleting a
            row from a table will not automatically change the table row
            value, so this should be updated to avoid possible errors.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     deleteTableEntry(tableName,roll)

         **Parameters**

         -  ``tableName`` - A string specifying the table from which the
            row will be removed.
         -  ``roll`` - An integer and the value that specifies the row
            to be removed.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:addTableEntry("test",1,3,"bert")]

                  #. .. code-block:: none

                        [r:deleteTableEntry("test",2)]

                  #. .. code-block:: none

                        [r:setTableRoll("test","")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `clearTable() </rptools/wiki/clearTable>`__
            `addTableEntry() </rptools/wiki/addTableEntry>`__
            `setTableRoll() </rptools/wiki/setTableRoll>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=deleteTableEntry&oldid=6731"

