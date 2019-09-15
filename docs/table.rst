.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=table
   |version=1.3b39
   |description=
   Gets the text value from the specified {{code|table}}. If the row is not specified then the default {{code|roll}} for the {{code|table}} is used. The row can be either a constant or a {{code|roll}}.

   Note that what this function returns is interpreted as either a string or a number. You can put code in a table entry but that too will be returned as a string and will not be evaluated. To evaluate the result you can use {{func|eval}} to evaluate e.g. the table entry {{code|1d5}} and {{func|evalMacro}} to evaluate e.g. the table entry {{code|[r:1d5]}}

   |usage=
   <source lang="mtmacro" line>
   table(name)
   table(name, row)
   tbl(name)
   tbl(name, row)
   </source>
   '''Parameters'''
   * {{code|name}} - A string containing the name of the [[Table|table]].
   * {{code|row}} - The row of the [[Table|table]] that should be returned.

   |examples=
   '''Example 1:''' Display a random value from table {{code|"tbl1"}} using default roll:
   <source lang="mtmacro" line>
   [r: table("tbl1")]
   </source>

   '''Example 2:''' Display the first value from table {{code|"tbl1"}}:
   <source lang="mtmacro" line>
   [r: table("tbl1", 1)]
   </source>

   '''Example 3:''' Display one of the first four values from {{code|"tbl1"}}, chosen randomly:
   <source lang="mtmacro" line>
   [r: table("tbl1", "1d4")]
   </source>

   '''Example 4:''' Display a table row that corresponds to a token property's value (the value must be numeric):
   <source lang="mtmacro" line>
   [r: table("tbl1", Intelligence)]
   [r: table("tbl1", getProperty("PCLevel"))]
   </source>

   '''Example 5:''' Evaluate the outcome of a table entry. The table entry '''must''' thus be something that can be evaluated, like {{code|1d10}} or {{code|roll(1,6)}} or {{code|3+5}}:
   <source lang="mtmacro" line>
   [r: eval(table("tbl1"))]
   </source>

   '''Example 5:''' Evaluate the outcome of a table entry that contains code. The table entry '''can''' thus contain code, but its not required. 'code' in this case is anything between [brackets]. An example table entry could be ''[h:roll=1d20]You [r:if(roll<10, 'hit', 'miss')] your target.'' :
   <source lang="mtmacro" line>
   [r: evalMacro(table("tbl1"))]
   </source>

   |also=
   {{func|tableImage}}

   There is a tool available to import tables from excel. You can find more about this [http://forums.rptools.net/viewtopic.php?f=3&t=11568#p124557 here]

   }}

`Category:Table Function <Category:Table_Function>`__
