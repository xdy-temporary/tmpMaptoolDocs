.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=createTable
   |version=1.4.0.1
   |trusted=true
   |description=
   Creates an empty table, specifying its access levels and optional image.
   |usage=
   <source lang="mtmacro" line>
   createTable(tableName, visible, accessible)
   createTable(tableName, visible, accessible, imageId)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|visible|Whether or not the table can be seen by players in the Table Window, {{true}} or {{false}}.}}
   {{param|accessible|Whether or not the table can be used by players to lookup values, {{true}} or {{false}}.}}
   {{param|imageId|Optional and is the asset id of an image that will be used for the table in the Table Window. If an invalid or missing asset id is used, the table will display a red "X".}}
   |examples=
   <source lang="mtmacro" line>
   [r:createTable("tableX",1,1)]
   [r:createTable("tableY",1,1,getTableImage("tableZ"))]

   </source>
   |also=
   {{func|addTableEntry}} {{func|setTableRoll}} {{func|deleteTable}}
   }}

`Category:Table Function <Category:Table_Function>`__
