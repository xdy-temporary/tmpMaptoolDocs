.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTableEntry
   |version=1.4.0.1
   |trusted=true
   |description=
   Sets the result for a specified roll value. Returns {{true}} if update successful and {{false}} if not. 
   |usage=
   <source lang="mtmacro" line>
   setTableEntry(tableName, roll, result)
   setTableEntry(tableName, roll, result, imageId)
   </source>
   '''Parameters'''
   {{param|tableName|A string containing the name of the Table.}}
   {{param|roll|A value to select the desired table entry.}}
   {{param|result|A string containing the result returned by the '''table()''' function.}}
   {{param|imageId|Optional and is the asset id of an image that will be returned by the '''tableImage()''' function.}}
   |also=
   [[table_(function)|table()]]
   }}

`Category:Table Function <Category:Table_Function>`__
