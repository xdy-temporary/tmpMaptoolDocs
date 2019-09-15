.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTableNames
   |version=1.4.0.1
   |description=Returns a list containing the names of the tables in the campaign. The type of the value returned depends on the delimiter parameter. The function can be used by players or from a non-trusted macro, but it will only return player-visible tables. When used by a GM or a trusted macro it returns all tables.

   |usage=
   <source lang="mtmacro" line>
   getTableNames()
   getTableNames(delim)
   </source>

   If {{code|delim}} is specified then it is used to separate the values in the list; if it is not specified then it defaults to "{{code|,}}".  When {{code|delim}} is the string "{{code|json}}" the return value will be in the form of a [[JSON_Array|JSON Array]].
   |examples=
   <source lang="mtmacro" line>
   [r:getTableNames()]
   [r:getTableNames("<br>")]
   [r:getTableNames("json")]
   </source>
   |also=
   [[Table|Table]], [[table_(function)|table()]]
   }}

`Category:Table Function <Category:Table_Function>`__
