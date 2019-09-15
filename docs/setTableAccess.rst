.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTableAccess
   |version=1.4.0.1
   |trusted=true
   |description=
   Sets whether or not the specified table is accessible to players.
   |usage=
   <source lang="mtmacro" line>
   setTableAccess(tableName, accessible)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|accessible|Whether or not the table can be accessed by players in the Table Window, {{true}} or {{false}}.}}
   |examples=
   <source lang="mtmacro" line>
   [h:setTableAccess("randomMonsters", 0)]
   </source>
   |also=
   {{func|getTableAccess}} {{func|getTableVisible}} {{func|setTableVisible}}
   }}

`Category:Table Function <Category:Table_Function>`__
