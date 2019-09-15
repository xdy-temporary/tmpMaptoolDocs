.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=tableImage
   |version=1.3b40
   |description=
   Gets the image asset value from the specified [[Table|table]]. If the row is not specified then the default [[Roll|roll]] for the [[Table|table]] is used.

   |usage=
   <source lang="mtmacro" line>
   tableImage(name)
   tableImage(name, row)
   tableImage(name, row, size)
   tblImage(name)
   tblImage(name, row)
   tblImage(name, row, size)
   </source>
   '''Parameters'''
   * {{code|name}} - A string containing the name of the [[Table|table]].
   * {{code|row}} - The row of the [[Table|table]] that should have the image asset returned.
   * {{code|size}} - The size the image asset returned should be. If the image is not square, this will be the size of the height.

   |examples=
   '''Example 1:''' Display a random image from [[Table|table]] {{code|"tbl1"}} using default [[Roll|roll]]:
   <source lang="mtmacro" line>
   <image src='[r: tableImage("tbl1")]'></image>
   </source>

   '''Example 1:''' Display the first image from [[Table|table]] {{code|"tbl1"}}: 
   <source lang="mtmacro" line>
   <image src='[r: tableImage("tbl1", 1)]'></image>
   </source>

   '''Example 2:''' Display one of the first four images, resized to {{code|40}} pixels tall, from {{code|"tbl1"}}, chosed randomly:
   <source lang="mtmacro" line>
   <image src='[r: tableImage("tbl1", "1d4", 40)]'></image>
   </source>

   |also=
   {{func|table}}
   }}

`Category:Table Function <Category:Table_Function>`__
