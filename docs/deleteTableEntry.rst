.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=deleteTableEntry
   |version=1.4.0.1
   |trusted=true
   |description=
   Removes a row from the specified table.

   '''Note:''' deleting a row from a table will not automatically change the table row value, so this should be updated to avoid possible errors.
   |usage=
   <source lang="mtmacro" line>
   deleteTableEntry(tableName,roll)
   </source>
   '''Parameters'''
   {{param|tableName|A string specifying the table from which the row will be removed.}}
   {{param|roll|An integer and the value that specifies the row to be removed.}}
   |examples=
   <source lang="mtmacro" line>
   [r:addTableEntry("test",1,3,"bert")]
   [r:deleteTableEntry("test",2)]
   [r:setTableRoll("test","")]
   </source>
   |also=
   {{func|clearTable}} {{func|addTableEntry}} {{func|setTableRoll}}
   }}

`Category:Table Function <Category:Table_Function>`__
