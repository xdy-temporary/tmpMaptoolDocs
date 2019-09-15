.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTableRoll
   |version=1.4.0.1
   |trusted=true
   |description=
   Sets the roll expression for the specified table.
   |usage=
   <source lang="mtmacro" line>
   getTableRoll(tableName, roll)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|roll|A string containing the new roll expression. If the value is "" the roll will be set to a default expression that should cover all table entries.}}
   |examples=
   <source lang="mtmacro" line>
   [r:setTableRoll("test","")]
   [r:setTableRoll("test","1d6+1")]
   </source>
   |also=
   {{func|getTableRoll}}
   }}

`Category:Table Function <Category:Table_Function>`__
