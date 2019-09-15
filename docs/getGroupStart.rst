.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getGroupStart
   |version=1.3b48
   |description=Returns the start index of the specified capture group for the specified match that was found using [[strfind|strfind()]]

   |usage=
   <source lang="mtmacro" line>
   getGroupStart(id, match, group)
   </source>
   Where 
   * id is the id returned by [[strfind|strfind()]]
   * match is the number of the match found by [[strfind|strfind()]]
   * group is the number of the capture group found by [[strfind|strfind()]]

   |example=
   <source lang="mtmacro" line>
   [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]
   match 1, group 1 start = [getGroupStart(id, 1, 1)]<br>
   match 1, group 2 start = [getGroupStart(id, 1, 2)]<br>
   match 2, group 1 start = [getGroupStart(id, 2, 1)]<br>
   match 2, group 2 start = [getGroupStart(id, 2, 2)]<br>
   </source>
   Returns
   <pre>
   match 1, group 1 start = 0 
   match 1, group 2 start = 5 
   match 2, group 1 start = 8 
   match 2, group 2 start = 10 
   </pre>
   }}

`Category:String Function <Category:String_Function>`__
