.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=addTableEntry
   |version=1.4.0.1
   |trusted=true
   |description=
   Adds a new row to the specified table.

   '''Note:''' adding a row to a table will not automatically change the table row value, so this should be updated to avoid possible errors (See {{func|setTableRoll}} function).
   |usage=
   <source lang="mtmacro" line>
   addTableEntry(tableName,rangeStart,rangeEnd,result)
   addTableEntry(tableName,rangeStart,rangeEnd,result,imageId)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|rangeStart|An integer indicating the lowest value that will return this row.}}
   {{param|rangeEnd|An integer indicating the highest value that will return this row.}}
   {{param|result|A string containing the result returned by the '''table()''' function.}}
   {{param|imageId|Optional and is the asset id of an image that will be returned by the '''tableImage()''' function.}}
   |examples=
   <source lang="mtmacro" line>
   [r:addTableEntry("test",1,3,"bert")]
   [r:addTableEntry("test",4,4,"fred")]
   [r:addTableEntry("test",5,5,"alf", getTokenImage())]
   [r:setTableRoll("test","")]
   </source>
   |also=
   {{func|setTableRoll}} {{func|table}} {{func|tableImage}} {{func|deleteTableEntry}}
   }}

`Category:Table Function <Category:Table_Function>`__
