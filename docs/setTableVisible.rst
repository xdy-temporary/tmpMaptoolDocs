.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTableVisible
   |version=1.4.0.1
   |trusted=true
   |description=
   Sets whether or not the specified table is visible to players.
   |usage=
   <source lang="mtmacro" line>
   setTableVisible(tableName, visible)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|visible|Whether or not the table can be seen by players in the Table Window, {{true}} or {{false}}.}}
   |examples=
   <source lang="mtmacro" line>
   [h:setTableVisible("randomMonsters", 0)]
   </source>
   |also=
   {{func|getTableVisible}} {{func|getTableAccess}} {{func|setTableAccess}}
   }}

`Category:Table Function <Category:Table_Function>`__
