.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTableEntry
   |proposed=false
   |deprecated=
   |trusted=true
   |version=1.5.4
   |description=
   Retrieves the raw table data for the specified entry as a JSON object. Returns an empty string if the entry doesn't exist.  If no image is associated with the entry the {{code|assetid}} will be an empty string.

   |usage=
   <source lang="mtmacro">
   getTableEntry(table, roll)
   </source>
   '''Parameters'''
   {{param|table|Name of table as a string.}}
   {{param|roll|The entry to retrieve as if a roll of that value had been made.}}

   |example=
   Get the entry from table "Critters" matching a roll of 4.
   <source lang="mtmacro" line>
   [r: getTableEntry("Critters", 4)]
   </source>
   Returns:
   <source lang="javascript">
   {"min":3, "max":5, "value": "duck", "assetid":""}
   </source>

   |also=
   {{func|addTableEntry}} {{func|setTableEntry}}

   }}

`Category:Table Function <Category:Table_Function>`__
