========================
createTable - MapToolDoc
========================

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

   .. rubric:: createTable
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

            -  `1 createTable()
               Function <#createTable.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: createTable() Function
            :name: createtable-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Creates an empty table, specifying its access levels and
            optional image.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     createTable(tableName, visible, accessible)

               #. .. code-block:: none

                     createTable(tableName, visible, accessible, imageId)

         **Parameters**

         -  ``tableName`` - A string containing the name of the Table.
         -  ``visible`` - Whether or not the table can be seen by
            players in the Table Window, ``true``\ (``1``) or
            ``false``\ (``0``).
         -  ``accessible`` - Whether or not the table can be used by
            players to lookup values, ``true``\ (``1``) or
            ``false``\ (``0``).
         -  ``imageId`` - Optional and is the asset id of an image that
            will be used for the table in the Table Window. If an
            invalid or missing asset id is used, the table will display
            a red "X".

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:createTable("tableX",1,1)]

                  #. .. code-block:: none

                        [r:createTable("tableY",1,1,getTableImage("tableZ"))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `addTableEntry() </rptools/wiki/addTableEntry>`__
            `setTableRoll() </rptools/wiki/setTableRoll>`__
            `deleteTable() </rptools/wiki/deleteTable>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=createTable&oldid=6730"

